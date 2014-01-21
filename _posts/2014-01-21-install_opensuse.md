---
layout: post
title: "install_OpenSuse"
description: ""
category: OpenSuse 的迁徙之路
tags: [linux,OpenSuse]
---
{% include JB/setup %}
以前一直用的linux版本都是ubuntu,记得ubuntu 13.10 出来的时候,兴冲冲的安装完成之后,一重启上来就是直接报错误了,心凉了半截.

`opensuse` 的最大特点就是__稳定__

#### 系统安装
> 刚装的移动的10M宽带,下载镜像速度飞快.

- 手头没有u盘,直接下载,直接刻盘安装.
- 安装过程没有什么好介绍了,Google 一大堆.

#### 桌面环境
- 推荐 gnome 和 kde, 但是我现在一直都是用的是`xfce4` __轻巧快速__.

#### 简单配置
- 软件源: 不知道opensuse用了什么黑科技,我系统里面的源是德国源,可是下载更新速度1M左右,几乎都是全速完成.没有必要切换镜像源.
- xfce 桌面环境,几乎没有包含什么多余的软件,装一个chrome 直接就可以用了.
- yast管理工具真的是太好用了,配置能力实在是太强大了.
- `xfce4-panel-plugin-whiskermenu`替换掉默认程序菜单
- 美化字体 `fontconfig-infinality ` 详细设置 [点击这里][1] [使用方法][2] 推荐 `osx 2 + LiHei pro` 字体渲染堪称完美,如果是双系统的话,最好把windows 下字体拷贝过来一份.具体路径    
```                
    Win c:\windows\Fonts\*  copy to LIN  /home/YOUR_USER_NAME/.fonts/
```
-  `sublime text 2` 安装和添加左键菜单项
    * [下载](http://www.sublimetext.com/2) 解压 ` tar -xvaf filename.tar.gz`
    * 移动 `sudo cp -a Sublime_Text_2 /opt/`
    * 建立软链接 `sudo ln -s /usr/bin/sublime /opt/Sublime_Text_2/sublimt_text`
    * 建立快捷方式 `cd /usr/share/applications/ && sudo touch sublime.desktop && sudo vim sublime.desktop`
    
        填写如下内容:

            [Desktop Entry]
            Version=2.0.2
            Name=Sublime Text
            GenericName=Text Editor
            
            Exec=sublime
            Terminal=false
            Icon=/opt/Sublime_Text_2/Icon/48x48/sublime_text.png
            Type=Application
            Categories=TextEditor;IDE;Development
            X-Ayatana-Desktop-Shortcuts=NewWindow
            
            [NewWindow Shortcut Group]
            Name=New Window
            Exec=sublime -n
            TargetEnvironment=Unity
    
    * 添加右键菜单打开`sudo sublime ~/.local/share/applications/mimeapps.list `添加一项目 `text/plain=sublime.desktop; `
    
- 另外就是美化换个主题之类,不细说,推荐一个组合比较好看[Zukitwo][3] + [elementary xfce icon theme][4]
- 多媒体编解码库下载,我直接安装了一个[vlc 教程][5].
- 更换oracle java [教程](http://www.suselinks.us/install-oracle-sun-java-1-7-opensuse-12-2)


#### 参考资料:
1. https://lug.ustc.edu.cn/sites/opensuse-guide/index.php


references:
[1]: http://vinsay.com/top-things-need-to-do-after-installing-opensuse-13-1/
[2]: http://www.webupd8.org/2013/06/better-font-rendering-in-linux-with.html
[3]: http://gnome-look.org/content/show.php/?content=140562
[4]: https://github.com/shimmerproject/elementary-xfce
[5]: http://en.opensuse.org/Additional_package_repositories#Packman
