# pip 使用方法

*<font size=4>pip 是 Python 包管理工具，该工具提供了对Python 包的查找、下载、安装、卸载的功能。目前如果你在 python.org 下载最新版本的安装包，则是已经自带了该工具。Python 2.7.9 + 或 Python 3.4+ 以上版本都自带 pip 工具。</font>*  
[pip 官网](https://pypi.org/project/pip/)

## 安装pip

**你可以通过以下命令来判断是否已安装：**  
pip --version  

**如果你还未安装，则可以使用以下方法来安装：**

**下载安装脚本**  
curl `https://bootstrap.pypa.io/get-pip.py` -o `get-pip.py`  

**运行安装脚本**  
sudo python `get-pip.py`  

*<font size=4>注意：用哪个版本的 Python 运行安装脚本，pip 就被关联到哪个版本，如果是 Python3 则执行以下命令：</font>*  

**<font size=4>运行安装脚本</font>**  
sudo python3 `get-pip.py`  

*<font size=4>一般情况 pip 对应的是 Python 2.7，pip3 对应的是 Python 3.x</font>*  

*<font size=4>Linux 发行版可直接用包管理器安装 pip，如 Debian 和 Ubuntu：</font>*  
<font size=4>sudo apt-get install python-pip</font>

## pip 最常用命令

**显示版本和路径**  
pip --version

**获取帮助**  
pip --help

**升级 pip**  
pip install -U pip

*<font size=4>如果这个升级命令出现问题 ，可以使用以下命令：</font>*  
<font size=4>sudo easy_install --upgrade pip</font>

**安装包**  
**最新版本**  
pip install SomePackage  
pip install SomePackage==1.0.4  

**最小版本**  
pip install 'SomePackage>=1.0.4'  

*<font size=4>比如我要安装 Django。用以下的一条命令就可以，方便快捷。</font>*  
<font size=4>pip install Django==1.7</font>

**升级包**
pip install --upgrade SomePackage
*<font size=4>升级指定的包，通过使用==, >=, <=, >, < 来指定一个版本号。</font>*  

**卸载包**  
pip uninstall SomePackage

**搜索包**  
pip search SomePackage

**显示安装包信息**  
pip show SomePackage

**查看指定包的详细信息**  
pip show -f SomePackage

**列出已安装的包**  
pip list

**查看可升级的包**  
pip list -o

<font size=4>*注意事项*  
*如果 Python2 和 Python3 同时有 pip，则使用方法如下：*  
*Python2：*  
python2 -m pip install XXX  
*Python3:*  
python3 -m pip install XXX</font>

## 设置pypi清华镜像
pip install pip -U  
pip config set global.index-url `https://pypi.tuna.tsinghua.edu.cn/simple`
