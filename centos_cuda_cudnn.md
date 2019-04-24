  yum install kernel-devel-$(uname -r) kernel-headers-$(uname -r)
  
To disable the Nouveau drivers, creating a file at "/usr/lib/modprobe.d/blacklist-nouveau.conf" with following content:

    blacklist nouveau
    options nouveau modeset=0
