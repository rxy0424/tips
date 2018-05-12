# 在安装Gentoo时的一些TIPS

1. 驱动 

在设置`/etc/portage/make.conf`时，加入`VIDEO_CARDS="nvidia"`可以在安装X server时自动安装显卡，也可以使用`emerge --ask x11-drivers/nvidia-drivers`安装

不要忘了在编译内核时选择声卡驱动，不然没有声音

2. 安装Vim

在`/etc/portage/package.use/vim`中写入,后再安装Vim和GVim
```
app-editors/gvim acl gnome gtk nls (aqua) cscope -debug gtk3 lua luajit motif neXt netbeans perl python racket ruby (selinux) session tcl
app-editors/vim  X acl gpm nls cscope -debug lua luajit -minimal perl python racket ruby (selinux) tcl terminal vim-pager
```

3. Hack emerge install porcess

    在`/etc/portage/env`中根据相应包的目录结构建立bash脚本，详细可见[Portage Document](https://dev.gentoo.org/~zmedico/portage/doc/)


4. 安装Cuda

    * Keyword changes
    
    在`/etc/portage/package.accept_keyword`中加入软件名可以安装其它Branch中的软件，例如
    ```
    dev-util/nvidia-cuda-toolkit
    dev-util/nvidia-cuda-sdk
    app-i18n/ibus-rime
    ```

    * USE changes

    在`/etc/portage/make.conf`中加入`USE="uvm"`
    在`/etc/portage/package.use/cuda`
    ```
    dev-util/nvidia-cuda-toolkit debugger profiler
    sys-libs/ncurses tinfo
    
    ```

    *  license changes

    在`/etc/portage/package.license`中加入
    ```
    www-client/google-chrome google-chrome
    dev-util/nvidia-cuda-toolket NVIDIA-CUDA
    ```

    * 更新`USE`

    使用`emerge --update --deeep --with-bdeps=y --newuse @world`

4. 有用的软件

    * app-portage/cpuid2cpuflags

    用来查看可用的CPU Flags
    ```
    echo "*/* $(cpuid2cpuflags)" > /etc/portage/package.use/00cpu-flags
    ```

    * gnome-terminal

    在gnome下用的terminal

    * Topicons plus

    gnome的插件，用来显示图标

    * cudnn

    安装时要将相应的文件放到`/usr/portage/distfiles`中

    * equery

    可以用来查询有哪些可能用的USE

    * qt-creator
    另忘了加上designer, 如果相安装examples，自己去`https://download.qt.io/online/qtsdkrepository/linux_x64/desktop/`下面找，
    并放在`qmake -query QT_INSTALL_EXAMPLES`中

    * p7zip

    to open .7z file
