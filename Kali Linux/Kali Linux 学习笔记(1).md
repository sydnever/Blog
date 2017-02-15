第一个系列的博客就是Kali Linux的学习笔记咯。

这个博客的内容粒度会以我自己对各种教程的理解为标准（比如提到XX官网，我就不会贴具体的地址），并非面向零基础和伸手党。

###0.安装

在官网下载的虚拟机镜像，解压后直接用对应虚拟机软件打开即可。在这里我使用的是VMware Pro 12.5。

官方虚拟机镜像默认密码是toor（在官方页面上有说明），建议安装成功后及时更改。

###1.换源

默认的桌面环境是gnome，所以默认的文本编辑器就是leafpad，我使用这个而不是Vim修改源列表。

终端启动快捷键并没有被设置，具体设置方法在下一部分讲解。

由于是以root用户登录的，所以在终端界面中一切命令都要小心谨慎。　


    leafpad /etc/apt/sources.list
清空sources.list文件内容，输入如下内容：

    #kali官方源
    deb http://http.kali.org/kali kali-rolling main non-free contrib
    #中科大的源
    deb http://mirrors.ustc.edu.cn/kali kali-rolling main non-free contrib
保存并退出，运行如下命令：

    apt-get update & apt-get upgrade
    apt-get dist-upgrade
经过一段时间长度取决于网速的终端滚动，完成了这一部分。

###2.初见

安装输入法

    apt-get install fcitx fcitx-googlepinyin fcitx-pinyin fcitx-module-cloudpinyin 
设置fcitx，将输入法添加即可。

安装flash player

    apt-get install flashplugin-nonfree
    update-flashplugin-nonfree --install

设置终端启动快捷键

设置-键盘-快捷键

添加快捷键，命令为：
    
    gnome-terminal
