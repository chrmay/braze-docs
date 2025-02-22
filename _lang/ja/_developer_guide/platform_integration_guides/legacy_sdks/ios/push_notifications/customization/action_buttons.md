---
nav_title: アクションボタン
article_title: iOS 用プッシュアクションボタン
platform: iOS
page_order: 1
description: "この参考記事では、iOS プッシュ通知にアクションボタンを実装する方法について説明します。"
channel:
  - push

noindex: true
---

{% multi_lang_include deprecations/objective-c.md %}

# アクションボタン {#push-action-buttons-integration}

Braze iOS SDK は、各プッシュアクションボタンの URL 処理サポートなど、デフォルトのプッシュカテゴリーをサポートしています。現在、デフォルトカテゴリーには、`Accept`/`Decline`、`Yes`/`No`、`Confirm`/`Cancel`、および `More` の4セットのプッシュアクションボタンがあります。 

![2つのカスタマイズ可能なアクションボタンを表示するためにプルダウンされているプッシュメッセージのGIF。][13]

デフォルトのプッシュカテゴリーを登録するには、統合手順に従ってください。

## ステップ1:Braze のデフォルトプッシュカテゴリーの追加

\[プッシュ登録][36] を行うときに、次のコードを使用してデフォルトのプッシュカテゴリーに登録します。

{% tabs %}
{% tab OBJECTIVE-C %}

```objc
// For UserNotification.framework (iOS 10+ only)
NSSet *appboyCategories = [ABKPushUtils getAppboyUNNotificationCategorySet];
[[UNUserNotificationCenter currentNotificationCenter] setNotificationCategories:appboyCategories];

// For UIUserNotificationSettings (before iOS 10)
NSSet *appboyCategories = [ABKPushUtils getAppboyUIUserNotificationCategorySet];
UIUserNotificationSettings *settings = [UIUserNotificationSettings settingsForTypes:UIUserNotificationTypeBadge
                                                                         categories:appboyCategories];
[[UIApplication sharedApplication] registerUserNotificationSettings:settings];
```

{% endtab %}
{% tab SWIFT %}

```swift
// For UserNotification.framework (iOS 10+ only)
let appboyCategories = ABKPushUtils.getAppboyUNNotificationCategorySet()
UNUserNotificationCenter.current().setNotificationCategories(appboyCategories)

// For UIUserNotificationSettings (before iOS 10)
let appboyCategories = ABKPushUtils.getAppboyUIUserNotificationCategorySet()
let settings = UIUserNotificationSettings.init(types: .badge, categories: appboyCategories)
UIApplication.shared.registerUserNotificationSettings(settings)
```

{% endtab %}
{% endtabs %}

バックグラウンドアクティベーションモードでプッシュアクションボタンをクリックすると、通知が閉じられるだけで、アプリは開きません。ユーザーが次回アプリを開くと、これらのアクションのボタンクリック分析がサーバーにフラッシュされます。

独自のカスタム通知カテゴリを作成する場合は、\[アクションボタンカスタマイズ][37]を参照してください。

## ステップ2:インタラクティブなプッシュ処理を有効にする

`UNNotification`フレームワークを使用し、Braze[delegates][39]を実装した場合、このメソッドはすでに統合されている必要があります。 

クリック分析や URL ルーティングを含むプッシュアクションボタンの処理を有効にするには、アプリの `(void)userNotificationCenter:didReceiveNotificationResponse:withCompletionHandler:` デリゲートメソッドに次のコードを追加します。

{% tabs %}
{% tab OBJECTIVE-C %}

```objc
[[Appboy sharedInstance] userNotificationCenter:center
                           didReceiveNotificationResponse:response
                               withCompletionHandler:completionHandler];
```

{% endtab %}
{% tab SWIFT %}

```swift
Appboy.sharedInstance()?.userNotificationCenter(center,
                                                didReceive: response,
                                                withCompletionHandler: completionHandler)
```

{% endtab %}
{% endtabs %}

UnNotification フレームワークを使用していない場合は、プッシュアクションボタンの処理を有効にするために、アプリの `application:handleActionWithIdentifier:forRemoteNotification:completionHandler:` に次のコードを追加する必要があります。

{% tabs %}
{% tab OBJECTIVE-C %}

```objc
[[Appboy sharedInstance] getActionWithIdentifier:identifier
                           forRemoteNotification:userInfo
                               completionHandler:completionHandler];
```

{% endtab %}
{% tab SWIFT %}

```swift
Appboy.sharedInstance()?.getActionWithIdentifier(identifier,
                                                 forRemoteNotification: userInfo,,
                                                 completionHandler: completionHandler)
```

{% endtab %}
{% endtabs %}

{% alert important %}
`handleActionWithIdentifier` を使用しているユーザーは、`UNNotification` フレームワークの使用を開始することを強くお勧めします。[`handleActionWithIdentifier`](https://developer.apple.com/documentation/uikit/uiapplicationdelegate/1623068-application?language=objc) が非推奨になったため、これをお勧めします。
{% endalert %}

## プッシュカテゴリのカスタマイズ

一連の\[デフォルトプッシュカテゴリ][2]]を提供することに加えて、Brazeはカスタム通知カテゴリとアクションsをサポートします。アプリケーションにカテゴリーを登録すると、Braze ダッシュボードを使用して通知カテゴリーをユーザーに送信できます。

`UserNotifications` フレームワークを使用していない場合は、[alternative categories][31] ドキュメントを参照してください。

その後、これらのカテゴリーをダッシュボードからプッシュ通知に割り当てて、デザインのアクションボタン構成をトリガーできます。デバイスに表示される `LIKE_CATEGORY` を活用する例を次に示します。

![「いいねを取り消す」と「いいね」の2つのプッシュアクションボタンを表示するプッシュメッセージ][17]


[13]: {% image_buster /assets/img_archive/iOS8Action.gif %}
[14]: https://developer.apple.com/reference/usernotifications/unnotificationcategory 「カテゴリードキュメント」
[17]: {% image_buster /assets/img_archive/push_example_category.png %}
guide/platform_integration_guides/ios/push_notifications/integration/#step-4-register-push-tokens-with-braze {{site.baseurl}}/developer_
 [37]:{{site.baseurl}}guide/platform_integration_guides/ios/push_notifications/customization/action_buttons/#push-category-customization
[39]: {{site.baseurl}}/developer_guide/platform_integration_guides/ios/push_notifications/integration/#step-5-enable-push-handling
[31]: https://developer.apple.com/documentation/usernotifications/unnotificationcategory
[2]: {{site.baseurl}}/developer_guide/platform_integration_guides/ios/push_notifications/customization/action_buttons/
