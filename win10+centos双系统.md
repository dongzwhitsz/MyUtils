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
    set root=hd(0,2)
    chainloader +1
    }

## (hd0,1),hd0表示第0块硬盘，1表示第一个分区，用来寻找你安装win10的地方，可能根据实际情况不相同，chainloader +1,别打错了，是+1

