# 在安装Gentoo时的一些TIPS

1.显卡驱动 

在设置`/etc/portage/make.conf`时，加入`VIDEO_CARDS="nvidia"`可以在安装X server时自动安装显卡，也可以使用`emerge --ask x11-drivers/nvidia-drivers`安装

2.安装Vim

在`/etc/portage/package.use/vim`中写入,后再安装Vim和GVim
```
app-editors/gvim acl gnome gtk nls (aqua) cscope debug gtk3 lua luajit motif neXt netbeans perl python racket ruby (selinux) session tcl
app-editors/vim  X acl gpm nls cscope -debug lua luajit -minimal perl python racket ruby (selinux) tcl terminal vim-pager
```
