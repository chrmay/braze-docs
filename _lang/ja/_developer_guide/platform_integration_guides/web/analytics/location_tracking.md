---
nav_title: 位置情報の追跡
article_title: ウェブのロケーショントラッキング
platform: Web
page_order: 5
page_type: reference
description: "この記事では、Web の位置情報の追跡を有効にする方法を説明します。"
tool: Location

---

# 位置情報の追跡

> この記事では、Web の位置情報の追跡を有効にする方法を説明します。

ユーザーの現在地を設定するには、geolocation APIの [`getCurrentPosition()`][0]メソッドを使用し、位置情報をBrazeに記録する：

```javascript
import * as braze from "@braze/web-sdk";
function success(position) {
  var coords = position.coords;
  braze.getUser().setLastKnownLocation(
    coords.latitude,
    coords.longitude,
    coords.accuracy,
    coords.altitude,
    coords.altitudeAccuracy
  );
}

navigator.geolocation.getCurrentPosition(success);
```

`navigator.geolocation.getCurrentPosition()` を呼び出すと、ユーザーがすでにアクセス許可を付与または拒否していない限り、直ちにユーザーにアクセス許可を要求します。ユーザーの最後の既知のロケーションを設定する方法については、[JSDocs][1] を参照してください。

## 単一のロケーションをログに記録する

Web SDKがBrazeサーバーにデータを送信する際、ユーザーの国がアプリケーションによって手動で設定されていない場合は、IPアドレスから自動的に検出される。

### 継続的な追跡

ページ読み込み中にユーザーの位置を継続的に追跡したい場合は、Geolocation APIの [`watchPosition()`](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation/watchPosition)メソッドを使う。このメソッドは、ユーザーの位置が更新されるたびに成功コールバックを呼び出す：

```javascript
function success(position) {
  var coords = position.coords;
  braze.getUser().setLastKnownLocation(
    coords.latitude,
    coords.longitude,
    coords.accuracy,
    coords.altitude,
    coords.altitudeAccuracy
  );
}

navigator.geolocation.watchPosition(success);
```

`navigator.geolocation.watchPosition()` を呼び出すと、ユーザーがすでにアクセス許可を付与または拒否していない限り、直ちにユーザーにアクセス許可を要求します。位置情報トラッキングの設定と停止については、[Mozilla開発者向けドキュメントを][2]参照のこと。

[0]: https://developer.mozilla.org/en-US/docs/Web/API/Geolocation/getCurrentPosition
[1]: https://js.appboycdn.com/web-sdk/latest/doc/classes/braze.user.html#setlastknownlocation
[2]: https://developer.mozilla.org/en-US/docs/Web/API/Geolocation/watchPosition
