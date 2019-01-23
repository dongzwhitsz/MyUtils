### 环境搭建

    测试环境：Python3.6  CentOS7
1、 pip install pynq
2、 sudo pip3 install --upgrade git+https://github.com/Xilinx/PYNQ.git
3、 pip install cffi netifaces pillow pyeda 
4、 安装pygraphviz（<a href = https://blog.csdn.net/chirebingxue/article/details/50393755>referenced link </a>）
        Step1:  <a href = https://graphviz.gitlab.io/_pages/Download/Download_source.html>下载Graphviz </a>
        安装Graphviz
        
        Step2.安装pygraphviz
        pip install pygraphviz --install-option="--include-path=/usr/include/graphviz" --install-option="--library-path=/usr/lib/graphviz/"
