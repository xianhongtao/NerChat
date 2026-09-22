# 桌面端指南

<!-- <img src="./nelemer_icon.png" style="max-height: 100px; margin-top:16px"/> -->
NerChat! 桌面端使用与 Element 官方相同的安装方式。在中国大陆可以直接访问 Element 官网，下载官方客户端，再改一下配置文件，就能默认连接 NerChat!。

## 安装指南

1. [下载Element Desktop](https://element.io/download)
2. 选择适合您操作系统的版本，并点击直接下载。
3. 下载、运行，对Linux用户请使用下面的包管理说明，按提示安装到系统中。
4. 此时先不要打开软件：如果不能访问 Matrix 主站，软件会报错。请先按下面的说明把配置文件添加到系统中，再打开。

## 配置方法

在以下路径中新建 `config.json`，把下面的内容保存进去：

```json
{
    "default_server_config": {
        "m.homeserver": {
            "base_url": "https://matrix.neboer.site:8448",
            "server_name": "chat.neboer.site"
        },
        "im.vector.riot.jitsi": {
            "preferredDomain": "meet.neboer.site"
        }
    },
    "brand": "NerChat!",
    "setting_defaults": {
        "breadcrumbs": true,
        "language": "zh-hans"
    },
    "map_style_url": "https://api.maptiler.com/maps/streets/style.json?key=fU3vlMsMn4Jb6dnEIFsx"
}
```

|操作系统|文件位置|
|:--:|:--:|
|Windows|%APPDATA%\Element\config.json|
|Linux|$XDG_CONFIG_HOME/Element/config.json 或 ~/.config/Element/config.json|
|MacOS|~/Library/Application Support/Element/config.json|

配置就绪后重启软件，就会默认连接到 NerChat!。
