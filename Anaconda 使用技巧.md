# Anaconda 使用方法

## References

[Anaconda 常用命令](https://www.jianshu.com/p/6d7de7a00b8d)

## Anaconda 常用命令

**查看已安装的包**  
conda list  
**更新所有包**  
conda upgrade --all  
**安装包**  
conda install package_name  
**删除包**  
conda remove package_name  
**更新包**  
conda update package_name  
**不知道包名要找包**  
conda search name  

## 虚拟环境

### 用conda建立

conda create -n env_name  list_of_packages

*<font size=4>其中 -n 代表 name，env_name 是需要创建的环境名称，list of packages 则是列出在新环境中需要安装的工具包。例如，当我安装了 Python3 版本的 Anaconda 后，默认的 root 环境自然是 Python3，但是我还需要创建一个 Python 2 的环境来运行旧版本的 Python 代码，最好还安装了 pandas 包，于是我们运行以下命令来创建:</font>*  

conda create -n py2 python=2.7 pandas

*<font size=4>细心的你一定会发现，py2 环境中不仅安装了 pandas，还安装了 numpy 等一系列 packages，这就是使用 conda 的方便之处，它会自动为你安装相应的依赖包，而不需要你一个个手动安装。</font>*

### 进入虚拟环境

source activate env_name

### 退出虚拟环境

source deactivate

### 删除名为 env_name 的环境

conda env remove -n env_name

### 显示所有的环境

conda env list

### 当分享代码的时候，同时也需要将运行环境分享给大家，执行如下命令可以将当前环境下的 package 信息存入名为 environment 的 YAML 文件中

conda env export > environment.yaml

### 使用别人生成的yaml文件创建环境

conda env create -f environment.yaml

## anaconda换源

**查看.condarc**  
sudo conda config --show-sources

**修改.condarc 位置从上面一步看 若找不到.condarc也可以先执行最后一步**  
sudo vim /home/username/.condarc

**改为下面**  
channels:  
&nbsp;&nbsp;\- defaults  
show_channel_urls: true  
default_channels:  
&nbsp;&nbsp;\- `https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main`  
&nbsp;&nbsp;\- `https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free`  
&nbsp;&nbsp;\- `https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/r`  
custom_channels:  
  conda-forge: `https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud`  
  msys2: `https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud`  
  bioconda: `https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud`  
  menpo: `https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud`  
  pytorch: `https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud`  
  simpleitk: `https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud`  

**执行**  
conda config --set show_channel_urls yes
