1. 安装好win10后，再安装centos
2. 安装centos时，要选择手动配置分区，不要自动配置分区
3. 安装完成之后，
>vim /boot/grub2/grub.cfg

在    

    ### BEGIN /etc/grub.d/30_os-prober ###
    ### BEGIN /etc/grub.d/30_os-prober ###

之间增加下面代码    
 
    menuentry 'win10'{
    insmod ntfs
    set root=(hd0,2)
    chainloader +1
    }

## (hd0,1),hd0表示第0块硬盘，1表示第一个分区，用来寻找你安装win10的地方，可能根据实际情况不相同，chainloader +1,别打错了，是+1

[参考链接](http://lib.csdn.net/article/linux/38477)


## 设置默认从win10启动


#### 一、修复引导win10：
1. 使用root身份(必须)打开 /boot/grub2/grub.cfg
2. 找到 ### BEGIN /etc/grub.d/30_os-prober ###
在后面添加
```
menuentry 'Windows 10' {
insmod ntfs
set root=(hd0,2)
chainloader +1
}
```
说明：set root=(hd0,1) 其中 hd0 表示硬盘，1表示C盘 ，我的win10装在C盘，它是sda1
3.保存重启

二、修改引导顺序：
    # grub2-set-default 'Windows 10' 验证默认启动项：
    # grub2-editenv list
输出：
    saved_entry=Windows 10


方法二

一、修复引导win10：
1、执行：
    $ sudo vi /etc/grub.d/40_custom
得到打开文件后，执行a进行编辑，
    #!/bin/sh
    exec tail -n +3 $0
    # This file provides an easy way to add custom menu entries. Simply type the 
    # menu entries you want to add after this comment. Be careful not to change
    # the  'exec tail' line above.
    menuentry 'Windows 10'{
    set root=(hd0,1)
    chainloader +1
    }
~
~
~
~
~
~
~
    "/etc/grub.d/40_custom" 9L,272C
按Esc，在按ZZ（或者Shift+：并输入wq），保存编辑并退出。
2、执行：
    $ grub2-mkconfig -o /boot/grub2/grub.cfg
生成grub.cfg文件。
3、最后，执行:
    $ reboot
重启既可以看到为windows10的引导了。



二、修改引导顺序：
    1. sudo vim /etc/default/grub
注释掉GRUB_DEFAULT=saved，在这一行的下面插入GRUB_DEFAULT='Windows 7'，保存并退出。然后执行
下面的命令
    2. sudo grub2-mkconfig --output=/boot/grub2/grub.cfg 
上面这句命令不能省，否则就算改了/etc/default/grub，也不会生效。

