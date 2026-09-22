---
head:
  - ['meta', { property: 'og:title', content: 'NerChat!——开源IM' }]
  - ['meta', { property: 'og:description', content: 'NerChat! 是一个部署在国内的即时聊天Matrix服务器。' }]
  - ['meta', { property: 'og:image', content: 'https://www.neboer.site/nerchat/wide_nerchat_logo.svg' }]
  - ['meta', { property: 'og:url', content: 'https://www.neboer.site/nerchat/' }]
  - ['meta', { property: 'og:type', content: 'website' }]

# https://vitepress.dev/reference/default-theme-home-page
layout: home

hero:
  name: "NerChat!"
  text: "Matrix 驱动的开源 IM"
  tagline: "NerChat! 是一个基于 Matrix 打造的自由、安全的即时通信平台，多年来专注于为国内用户提供服务。"
  actions:
    - theme: brand
      fontawesome: ['fab', 'chrome']
      text: 浏览器访问
      # link: /docs/client/desktop-client
      link: https://chat.neboer.site/
      browser_type: desktop
    - theme: brand
      fontawesome: ['fab', 'android']
      text: 安卓客户端
      link: /docs/client/nelement
      browser_type: Android
    - theme: brand
      fontawesome: ['fab', 'apple']
      text: 苹果用户指南
      link: /docs/client/ios-instructions
      browser_type: iOS
    - theme: alt
      fontawesome: ['fas', 'mobile-screen']
      text: 其他客户端
      link: /docs/client/available-clients
    - theme: alt
      fontawesome: ['far', 'file']
      text: 阅读文档
      link: /docs/
  image:
    src: /nerchat_logo.svg
    alt: NerChat! logo

features:
  - title: 开源
    icon: 
      fontawesome: ['fas', 'code']
    details: NerChat! 基于 Matrix 与 Element Web 搭建，服务端和客户端的代码完全开源。
  - title: 安全
    icon:
      fontawesome: ['fas', 'lock']
    details: 继承 Matrix 的优势，采用非对称加密，聊天内容只有对话的参与者能看到，其他任何人都无法获取。
  - title: 现代
    icon: 
      fontawesome: ['fas', 'rocket']
    details: Element 客户端功能全面、界面美观，支持语音、图片、代码、数学公式、Markdown、文件等多种消息，也支持视频会议。
  - title: 活跃
    icon: 
      fontawesome: ['fas', 'fire']
    details: Matrix 社区非常活跃，开发者众多，也是开放安全聊天系统领域最顶尖的团队之一，功能迭代很快。
  - title: 维护
    icon: 
      fontawesome: ['fas', 'wrench']
    details: NerChat! 由 UntilSoftware 维护。UntilSoftware 是一个由敬业、专业的开源开发者组成的开源组织，长期负责解决各类技术问题。
  - title: 本地化
    icon: 
      fontawesome: ['fas', 'globe']
    details: NerChat! 针对中国大陆的网络环境做了专门的访问优化，无需额外配置，访问流畅。
  - title: 跨平台
    icon: 
      fontawesome: ['fas', 'mobile-screen']
    details: Web、Windows、Linux、macOS、Android、iOS 等平台全覆盖，多端随时畅聊。
  - title: 开放
    icon: 
      fontawesome: ['fas', 'users']
    details: 兼容所有 Matrix 协议软件，NerChat! 发布的客户端也能连接其他 Matrix 服务器，希望为优秀开源技术的本地化尽一份力。
---
