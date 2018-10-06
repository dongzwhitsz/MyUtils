# 我的samba4搭建的过程 
<br>
## 第一次安装samba是在Unbutu下面,还有很多缺陷

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
    
    #启动或者重启samba服务
    /etc/init.d/smbd start
    /etc/init.d/smbd restart
    
samba4以前的samba版本中该项可以设置为share，但在samba4中如果设置为share，会因为配置文件错误无法启动samba服务，因为share和server已经被废弃

    security = user
    map to guest = Bad User
    
通过以上配置之后可以直接在windows中访问设置的分享文件，不用输入密码，<br>
如果要配置为用户登陆模式需要添加系统中已存的用户于samba用户中
>smbpasswd -a user-name  


## 第二次安装在centos下面
>yum install samba

>cd /etc/samba  
 cp smb.cnof smb.conf.bak

配置samba服务文件

    workgroup = WORKGROUP
    [dongzw centos shares]  #共享显示的目录名
    comment = anything you like to
    path = /mnt/Shares   #设置共享的目录
    writable = yes #设置可写
    browseable = yes

重启samba服务
>systemctl restart smb

改变共享文件夹的权限
>chmod 777 Shares

增加防火墙可允许的服务
>firewall-cmd --permanent --add-port=139/tcp  
 firewall-cmd --permanent --add-port=445/tcp
 
修改selinux的权限或者直接关闭selinux

