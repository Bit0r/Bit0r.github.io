# 命令行选项

chrome有很多命令行选项，有些选项非常实用，这里介绍一些。

## 减少cpu和内存消耗

以下选项可以显著减少cpu和内存消耗，但是会使得debugger和插件的功能出现问题，所以不适合开发者使用

```fish
google-chrome --in-process-gpu --process-per-site --in-process-plugins
```

## 给予插件更高的权限

以下选项可以给予插件更高的权限，比如可以再商店中运行插件，可以运行不安全的脚本，可以运行过期的插件

```fish
google-chrome --allow-running-insecure-content --allow-outdated-plugins --allow-scripting-gallery --silent-debugger-extension-api
```

## 开启调试模式

以下选项可以开启调试模式，可以通关端口9222进行页面调试

```fish
google-chrome --remote-debugging-port=9222
```

## 设置代理

以下是chrome设置代理的选项用法

```fish
google-chrome --proxy-server=socks5://localhost	# chrome只能使用socks5代理，不能使用socks5h代理
google-chrome --proxy-server=http://localhost:8800	# http代理
```

## 无法使用语音朗读(TTS)

Linux下的electron应用无法使用语音朗读，这是因为electron没有安装语音朗读引擎。
需要先安装语音朗读引擎 `espeak-ng` 和 `speech-dispatcher`，然后使用以下选项

```fish
electron --enable-speech-dispatcher
```

# 添加到.desktop文件

1.在应用程序菜单找到chrome启动器图标

![菜单](menu.avif)

2.在图标上右键，选择“编辑应用程序”

3.在“应用程序”选项卡中，找到“命令”输入框，添加上面的选项

![编辑应用程序](edit.avif)
