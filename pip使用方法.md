- [安装pip](#%e5%ae%89%e8%a3%85pip)
- [pip 最常用命令](#pip-%e6%9c%80%e5%b8%b8%e7%94%a8%e5%91%bd%e4%bb%a4)
- [设置pypi清华镜像](#%e8%ae%be%e7%bd%aepypi%e6%b8%85%e5%8d%8e%e9%95%9c%e5%83%8f)

---

*<font size=2>pip 是 Python 包管理工具，该工具提供了对Python 包的查找、下载、安装、卸载的功能。目前如果你在 python.org 下载最新版本的安装包，则是已经自带了该工具。Python 2.7.9 + 或 Python 3.2+ 以上版本都自带 pip 工具。*  
[pip 官网](https://pypi.org/project/pip/)</font>

---

# 安装pip

你可以通过以下命令来判断是否已安装：

```shell
pip --version  
```

如果你还未安装，则可以使用以下方法来安装：

下载安装脚本

```shell
curl <https://bootstrap.pypa.io/get-pip.py> -o get-pip.py  
```

运行安装脚本

```shell
sudo python get-pip.py  
# 注意：用哪个版本的 Python 运行安装脚本，pip 就被关联到哪个版本，如果是 Python3 则执行以下命令：
# 运行安装脚本  
sudo python3 get-pip.py</font>  
#一般情况 pip 对应的是 Python 2.7，pip3 对应的是 Python 3.x
```

Linux 发行版可直接用包管理器安装 pip，如 Debian 和 Ubuntu：

```shell
sudo apt-get install python-pip
```

---

# pip 最常用命令

显示版本和路径

```shell
pip --version
```

获取帮助  

```shell
pip --help
```

升级 pip  

```shell
pip install -U pip
# 如果这个升级命令出现问题 ，可以使用以下命令：  
sudo easy_install --upgrade pip
```

安装包  

```shell
# 最新版本  
pip install SomePackage  
pip install SomePackage==1.0.2  

# 最小版本  
pip install 'SomePackage>=1.0.2'  

# 比如我要安装 Django。用以下的一条命令就可以，方便快捷。
pip install Django==1.7
```

升级包

```shell
pip install --upgrade SomePackage
# 升级指定的包，通过使用==, >=, <=, >, < 来指定一个版本号。
```

卸载包  

```shell
pip uninstall SomePackage
```

搜索包  

```shell
pip search SomePackage
```

显示安装包信息  

```shell
pip show SomePackage
```

查看指定包的详细信息  

```shell
pip show -f SomePackage
```

列出已安装的包  

```shell
pip list
```

查看可升级的包  

```shell
pip list -o
```

**注意事项**
如果 Python2 和 Python3 同时有 pip，则使用方法如下：  

```shell
# Python2：  
python2 -m pip install XXX  
# Python3:  
python3 -m pip install XXX
```

---

# 设置pypi清华镜像

```shell
pip install pip -U  
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
```
