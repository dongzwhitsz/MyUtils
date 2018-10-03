# ubuntu 部署NFS
确保没有防火墙的拦截之后
>apt-get install rpcbind
apt-get install nfs-kernel-server

编辑配置文件 
>vim /etc/exports
