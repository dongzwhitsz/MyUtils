### 环境搭建

测试环境：Python3.6  CentOS7
 
    pip install pynq
    pip install --upgrade git+https://github.com/Xilinx/PYNQ.git
    pip install cffi netifaces pillow pyeda 
安装pygraphviz（<a href = https://blog.csdn.net/chirebingxue/article/details/50393755>referenced link </a>）

 step1:  <a href = "https://graphviz.gitlab.io/_pages/Download/Download_source.html">下载安装Graphviz </a><br>
 step2.  <a href = "https://blog.csdn.net/chirebingxue/article/details/50393755">安装pygraphviz</a>

        pip install pygraphviz --install-option="--include-path=/usr/include/graphviz" --install-option="--library-path=/usr/lib/graphviz/"
