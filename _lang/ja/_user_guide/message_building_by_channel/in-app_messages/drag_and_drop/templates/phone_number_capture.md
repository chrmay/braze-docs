---
nav_title: SMSおよびWhatsAppサインアップフォーム
article_title: SMSおよびWhatsAppサインアップフォーム
alias: "/phone_number_capture/"
description: "このリファレンスページでは、SMSおよびWhatsAppのサインアップフォームをアプリ内メッセージのドラッグアンドドロップエディタで作成する方法について説明します。"
---

# SMSとWhatsAppのサインアップフォーム

> SMSおよびWhatsAppサインアップフォームは、アプリ内メッセージ用のドラッグアンドドロップエディターで利用できるテンプレートです。これらのテンプレートを使用してユーザーの電話番号を収集し、SMSおよびWhatsAppのサブスクリプショングループを成長させましょう。

![電話サインアップフォームテンプレートを使用して作成されたアプリ内メッセージの3つの例。]\[img7]

## SDK の要件

### 最小の SDK バージョン

ドラッグアンドドロップエディタを使用して作成されたメッセージは、次の最小SDKバージョンのユーザーにのみ送信できます。詳細と注意点については、[前提条件][1]セクションの[ドラッグアンドドロップでアプリ内メッセージを作成する]({{site.baseurl}}/user_guide/message_building_by_channel/in-app_messages/drag_and_drop/create/)を参照してください。

{% sdk_min_versions swift:5.0.0 android:8.0.0 web:2.5.0 %}

### テキストリンクのSDKバージョン

メッセージを閉じないテキストリンクを含めたい場合、ユーザーは次の最小SDKバージョンを使用している必要があります:

{% sdk_min_versions swift:6.2.0 android:26.0.0 %}

{% alert warning %}
アプリ内メッセージにURLにリダイレクトするリンクを含め、エンドユーザーが指定された最小SDKバージョンに達していない場合、リンクをクリックするとメッセージが閉じられ、ユーザーはフォームを送信するためにメッセージに戻ることができなくなります。
{% endalert %}

## 電話番号登録フォームの作成

ドラッグアンドドロップのアプリ内メッセージを作成する際は、テンプレートに**SMSサインアップ**または**WhatsAppサインアップ**を選択してください。

![アプリ内メッセージを作成する際に、SMSサインアップまたはWhatsAppサインアップをテンプレートとして選択するためのモーダル。]\[img2]{: style="max-width:70%"}

これらのテンプレートは、モバイルアプリとWebブラウザの両方でサポートされています。

### ステップ 1:メッセージスタイルを設定する

テンプレートをカスタマイズする前に、サイドメニューを使用してメッセージ全体のメッセージレベルのスタイルを設定できます。例えば、メッセージに含まれるすべてのテキストのフォントやすべてのリンクの色をカスタマイズしたい場合があります。メッセージをモーダルまたは全画面表示タイプにすることもできます。

![カスタムフォントのアップロードと選択のワークフロー。]\[img6]

### ステップ2:電話番号入力コンポーネントをカスタマイズする

サインアップフォームの作成を開始するには、エディタで電話番号入力コンポーネントを選択します。

![電話番号入力コンポーネントが選択された状態でサインアップフォームを作成する際のプレビューエリア。]\[img3]{: style="max-width:40%"}

サイドメニューから、このテンプレートが電話番号を収集するサブスクリプショングループを指定します。コンプライアンスのベストプラクティスに従うために、電話番号のサインアップフォームごとに1つのサブスクリプショングループへの同意のみを収集できます。ただし、必要に応じて、他のサブスクリプショングループの同意を収集するために複数のフォームを使用することができます。

![サブスクリプショングループドロップダウンにサブスクリプショングループが選択されています。]\[img4]{: style="max-width:40%"}

デフォルトでは、私たちはグローバルに数値を収集しますが、収集する国の数を制限することができます。これは、特定の国の電話番号を持つユーザーにのみメッセージを送信する場合に役立ち、リストの清潔さを保つのに役立ちます。そのためには、**すべての国から番号を収集する**をオフにして、ドロップダウンを使用して特定の国を選択します。ユーザーは、あなたが明示的に追加した国のみを選択できるようになります。

![国のドロップダウンから、番号を収集したい国を選択します。]\[img5]{: style="max-width:40%"}

#### 無効な電話番号

ユーザーが受け入れられない特殊文字を含む電話番号を入力した場合、カスタマイズできない一般的なエラー指標が表示され、フォームを送信できません。**プレビュー & テスト** タブおよびテストデバイスでエラーの動作を確認できます。この記事を参照して、[Brazeが電話番号をフォーマットする方法][2]を学んでください。

### ステップ 3:免責事項の言語を追加する（SMSサインアップフォーム用）

SMSサインアップフォームでは、送信するSMSの種類を明確に伝えることが重要です。フォームに次の情報を含めることで、リストの成長がコンプライアンスに準拠していることを確認してください:

- お客様が受け取る可能性のあるSMSメッセージの種類の説明（カートのリマインダー、プロモーションやお得情報、予約のリマインダーなど）。すべてのユースケースを列挙する必要はありませんが、ブランドが送信するメッセージの種類について説明する必要があります。
- 同意は購入の条件ではないことに注意してください（該当する場合）。
- メッセージの頻度とメッセージおよびデータ料金が適用されることを思い出させる。正確なメッセージ頻度がわからない場合は、頻度が変動する可能性があると言うことができます。
- 利用規約およびSMSプライバシーポリシーへのリンク。
- ヘルプとオプトアウトキーワードのリマインダー（ヘルプの場合はHELP、キャンセルするにはSTOP）。

テンプレートにプレースホルダーの免責事項を例として提供していますが、これは法的助言を構成するものではなく、コンプライアンスの目的で依拠すべきではありません。あなたの特定のブランドに合わせた言語を開発するために、法務チームと協力することが重要です。

{% alert note %}
このドキュメントは、法的助言を提供することを意図しておらず、完全に依存することはできません。
{% endalert %}

詳細については、[SMSの法律と規制][4]を参照してください。

### ステップ 4:メッセージにスタイルを設定する

ドラッグアンドドロップ[アプリ内メッセージコンポーネント][3]を使用して、メッセージの外観と感触をカスタマイズできます。

## レポート

キャンペーンが開始された後、リアルタイムで結果を分析して、キャンペーンにどれだけのユーザーが関与したかを確認できます。サブスクリプショングループにオプトインしたユーザーの数を確認するには、アプリ内メッセージを受信し、フォームを送信したユーザーをフィルタリングして、サブスクリプショングループにサブスクライブしたユーザーの[Segment][5]を作成できます。

![アプリ内メッセージパフォーマンスパネルは、アプリ内メッセージ内の各リンクのクリック数を表示します。]\[img8]

[1]: {{site.baseurl}}/user_guide/message_building_by_channel/in-app_messages/drag_and_drop/create/#prerequisites
[2]: {{site.baseurl}}/user_guide/message_building_by_channel/sms/phone_numbers/user_phone_numbers/#importing-phone-numbers
[3]: {{site.baseurl}}/user_guide/message_building_by_channel/in-app_messages/drag_and_drop/create/#drag-and-drop-in-app-message-components
[4]: {{site.baseurl}}/user_guide/message_building_by_channel/sms/sms_laws_and_regulations/
[5]: {{site.baseurl}}/user_guide/engagement_tools/segments/creating_a_segment/

\[img1]: {% image_buster /assets/img_archive/dnd_iam_phone_capture_example.png %}
\[img2]: {% image_buster /assets/img_archive/dnd_iam_phone_capture_template.png %}
\[img3]: {% image_buster /assets/img_archive/dnd_iam_phone_capture_select.png %}
\[img4]: {% image_buster /assets/img_archive/dnd_iam_phone_capture_subscription.png %}
\[img5]: {% image_buster /assets/img_archive/dnd_iam_phone_capture_countries.png %}
\[img6]: {% image_buster /assets/img_archive/dnd_iam_phone_capture_custom_font.gif %}
\[img7]: {% image_buster /assets/img_archive/dnd_iam_phone_capture_example2.png %}
\[img8]: {% image_buster /assets/img_archive/dnd_iam_phone_capture_analytics.png %}
