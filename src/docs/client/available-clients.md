# 客户端

在桌面浏览器中打开 NerChat! 网页版 chat.neboer.site，或者安装官方安卓客户端 Nelement，都可以直接登录。这两种方式是我们推荐的：无需额外配置，像国产聊天软件一样开箱即用。

::: warning

NerChat! 网页版只支持桌面浏览器使用，移动端请使用 App，不要直接用手机浏览器访问网站。

桌面端推荐使用 Chrome 和 Firefox，请尽量避免使用国产浏览器连接。

:::

如果您不想使用 NerChat! 提供的客户端，任何支持 Matrix 协议的客户端（如 Element Android）都可以登录——只需把 homeserver 地址设置为 **chat.neboer.site**。不过您需要先解决官方 App 可能无法连接 **element.io** 的问题。

反过来，用 NerChat! 发布的客户端也可以连接任何支持 Matrix 协议的服务器；只是受中国网络限制，包括 matrix.org 在内的一些站点可能无法直接访问。

按您使用的平台，点击下表中的客户端名称即可下载。受网络环境影响，官方客户端的网站可能无法直接访问。

|使用环境|推荐客户端|官方客户端|备选客户端|
|:--:|:--:|:--:|:--:|
|Web|[chat.neboer.site](https://chat.neboer.site)|[app.element.io](https://app.element.io)|-|
|Windows/Linux/macOS|[Element Desktop](https://packages.riot.im/desktop/install/win32/x64/Element%20Setup.exe)|[Element Desktop](https://packages.riot.im/desktop/install/win32/x64/Element%20Setup.exe)|-|
|Android|[Element X](https://f-droid.org/packages/io.element.android.x/)|[Element X](https://play.google.com/store/apps/details?id=io.element.android.x)|[Nelement](nelement)|
|iOS|[Element X](https://apps.apple.com/us/app/element-x-secure-chat-call/id1631335820)|[Element X](https://apps.apple.com/us/app/element-x-secure-chat-call/id1631335820)|[Element Classic](https://apps.apple.com/us/app/element-classic/id1083446067)|

在桌面端，Element Desktop 的消息推送最快。

移动端的推送通过 FCM 和 APNs 实现，相对省电，但可能存在一定延迟。没有 Google Play 服务的安卓设备可能收不到推送，这是大陆网络环境导致的，目前还没有解决办法。如果您很在意推送的即时性，可以开启 Element X / Nelement 的常驻后台选项，并在电池优化中将其忽略。

具体操作方法可以参考所用 App 中的设置项。
