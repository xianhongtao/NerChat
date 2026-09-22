# Nelement安全性

为了方便更多安卓用户，我们在 Element Android 源码基础上做了少量修改，发布了 Nelement，以解决 Element 默认服务器无法更改、给中国用户带来不便的问题。某种程度上，Nelement 也代表了 NerChat! 的立场。

Element Android 是开源软件，Nelement 也是。再次说明：Nelement 的源代码可以在 [github.com/Neboer/Nelement](https://github.com/Neboer/Nelement) 找到。它与 Element Android 使用相同的开源协议，只是家服务器配置不同——中国大陆的朋友打开即可连接到 NerChat!，不必等 Element 直连超时后再去改服务器地址。

Nelement 的唯一发布渠道是 GitHub Release，我们不提供应用商店、Google Play、付费或网盘等下载方式。按照 Apache 协议的要求，您可以在保证安装包完整的前提下自由分发 Nelement 的源代码和可安装软件。

## Nelement对Element Android的修改

Nelement主要修改了Element Android的四处代码：

1. Nelement修改了Element Android的家服务器配置文件，修改默认服务器、bug报告包名等信息。

    参考这个 [commit](https://github.com/Neboer/Nelement/commit/30857e2f) 中的[文件修改](https://github.com/Neboer/Nelement/commit/30857e2f#diff-5db79790a9dbb104c9d1687b291b21b55bc9ae1736d6a83251e1de6a012911bf)。

2. Nelement修改了Element Android的图标、包名和应用名，与原版软件做出了重要区分，并且可以和原软件共存。

    对图标和应用名的修改在同[一个 commit](https://github.com/Neboer/Nelement/commit/30857e2f) 的其余改动中。

    对包名的修改请参考这个 [commit](https://github.com/Neboer/Nelement/commit/b5a5a4e8) 中的[文件修改](https://github.com/Neboer/Nelement/commit/b5a5a4e8#diff-7d90e090118cb3b19ed7934b93c3b7ce8235f64f4fe186d2ea3f83fee00bf03e)。

3. Nelement 调整了 Element Android 的构建流程，直接构建 F-Droid 版本，而不再编译 Google Play 预编译版本——Nelement 不会发布到 Google Play 商店，这样也避免了没有 Google Play 框架的国产手机在使用中出问题。

    相关改动主要在[这个 commit](https://github.com/Neboer/Nelement/commit/afc7636f) 中：它删掉了 Element Android 里不必要的测试、发布等 CI 流程，只保留 F-Droid Release 版本的构建代码。

4. Nelement 把 Element Android 中默认的 Jitsi 会议服务器地址改为我们在国内搭建的 Jitsi 服务，让用户可以享受高品质、低延迟的语音通话体验。

    参考这个[commit](https://github.com/Neboer/Nelement/commit/5efdb741)。

我们还做了一些适配性的小改动，例如修改 google-services.json 中的包名、调整 manifest 文件中的相关注册信息、使用 Neboer 自己的密钥给 Nelement 签名，以及修改 Element 的版本号等。

## Nelement代码审查

Nelement 的代码完全基于 Element Android 项目修改而来，所有改动都可以直接[在 GitHub 上查看](https://github.com/vector-im/element-android/compare/main...Neboer:Nelement:main)。
我们相信，各位有足够的能力或信任，来认可 Nelement 为安全所做的努力。

当然，您也完全可以不信任我们：被改过的客户端不仅能窃取您的隐私，还可能让所有加密瞬间失效——我们完全可以在客户端里截留您的消息，悄悄发到服务器上。也正因如此，客户端的开源透明同样重要，Nelement 必须做到开源透明，才能尽可能赢得大家的信任。

Nelement的软件发布流程如下：

1. （来自上游）Element Android上游发布新版本Release。
2. Nelement的维护者收到Release通知，目前NerChat!里负责维护Nelement的主要开发者是Neboer。
3. Neboer向Nelement发起pull request，申请将element/main分支合并到Nelement/main分支。
4. Neboer在本地合并两个分支，更新代码，解决冲突，做出修改。
5. Neboer提交修改，同时将修改push到Neboer/Nelement仓库中。
6. commit行为触发了GitHub Actions中配置好的CI，编译过程启动，自动构建无签名的Release版本的安装包。
7. GitHub Release 构建完成后，Neboer 把 Release 中生成的 artifact（即编译产出的未签名安装包）下载到本地，用自己的密钥签名。
8. Neboer发布新版本的GitHub Release，将签名完毕的Nelement安装包以assets的形式添加到其中。
9. NerChat!发布服务器通知，告知大家新版本的Nelement已经发布，可以下载。

可以看到，整个过程中我们无法改动 Nelement 的代码：您在软件发布后下载 GitHub Actions 生成的 artifact，与 Release 版本比对即可——除签名外，两个压缩包中的所有文件都应当完全相同。Nelement 的安全性由 GitHub Actions 保证。

## 可信的Nelement获取渠道

NerChat! 只通过 GitHub Release 发布 Nelement，不少国内用户下载有困难。为了让 NerChat! 更易于传播，我们允许用户在 Apache 协议许可下自由分发 Nelement 的资源。下面列出了目前得到维护团队认可的发布渠道；如果您在其他应用商店或网盘分享中看到 Nelement 的安装包，请及时告诉我们，谢谢。

如果您想成为Nelement在某个平台的新的发布者，请直接在NerChat!中与我们取得联系。

以下是目前已知的、会定期更新且可以信任的Nelement第三方发布渠道：

- [GitHub Release](https://github.com/Neboer/Nelement)
