<h1> 我的samba搭建的过程 </h1>

    apt install samba   #安装samba
    cd /etc/samba       #进入到samba的配置目录
    cp smb.conf smb.conf.bak    #备份samba的配置文件 
    vim smb.conf
    #在文件的末尾配置共享目录
    [dongzw ubuntu shares]  #共享显示的目录名
    comment = anything you like to
    path = /opt   #设置共享的目录
    writable = yes #设置可写
    
    #改变文件的读写权限
    chmod 777 /opt