>1、删除HKEY_CURRENT_USER\Software\Microsoft\SystemCertificates\Root\ProtectedRoots </br>
>2、删除HKEY_CURRENT_USER\Software\Microsoft\SystemCertificates\Root\Certificates </br>
>3、删除HKEY_CURRENT_USER\Software\Microsoft\SystemCertificates\Root</br>


可以参照以下步骤1、2、3、4操作：
>步骤1、打开注册表，点开始菜单，点运行，输入regedit.exe后回车</br>
>找到注册表键值HKEY_CURRENT_USER\Software\Microsoft\SystemCertificates\Root\ProtectedRoots </br>
>右键点权限，（如果有弹窗，点重新排序，不是每台电脑都会遇到），把所有用户名（下图4个）都设置成完全控制权限，点确定，右键ProtectedRoots，点删除</br>



本文来自 克豪 的CSDN 博客 ，全文地址请点击：https://blog.csdn.net/qq754772661/article/details/81452131?utm_source=copy 
