# 目录

- [目录](#%e7%9b%ae%e5%bd%95)
- [References](#references)
- [Anaconda 常用命令](#anaconda-%e5%b8%b8%e7%94%a8%e5%91%bd%e4%bb%a4)
  - [查看已安装的包](#%e6%9f%a5%e7%9c%8b%e5%b7%b2%e5%ae%89%e8%a3%85%e7%9a%84%e5%8c%85)
  - [更新所有包](#%e6%9b%b4%e6%96%b0%e6%89%80%e6%9c%89%e5%8c%85)
  - [安装包](#%e5%ae%89%e8%a3%85%e5%8c%85)
  - [删除包](#%e5%88%a0%e9%99%a4%e5%8c%85)
  - [更新包](#%e6%9b%b4%e6%96%b0%e5%8c%85)
  - [不知道包名要找包](#%e4%b8%8d%e7%9f%a5%e9%81%93%e5%8c%85%e5%90%8d%e8%a6%81%e6%89%be%e5%8c%85)
- [虚拟环境](#%e8%99%9a%e6%8b%9f%e7%8e%af%e5%a2%83)
  - [用conda建立](#%e7%94%a8conda%e5%bb%ba%e7%ab%8b)
  - [进入虚拟环境](#%e8%bf%9b%e5%85%a5%e8%99%9a%e6%8b%9f%e7%8e%af%e5%a2%83)
  - [退出虚拟环境](#%e9%80%80%e5%87%ba%e8%99%9a%e6%8b%9f%e7%8e%af%e5%a2%83)
  - [删除名为 env_name 的环境](#%e5%88%a0%e9%99%a4%e5%90%8d%e4%b8%ba-envname-%e7%9a%84%e7%8e%af%e5%a2%83)
  - [显示所有的环境](#%e6%98%be%e7%a4%ba%e6%89%80%e6%9c%89%e7%9a%84%e7%8e%af%e5%a2%83)
  - [环境分享](#%e7%8e%af%e5%a2%83%e5%88%86%e4%ba%ab)
- [anaconda换源](#anaconda%e6%8d%a2%e6%ba%90)

---

# References

[Anaconda 常用命令](https://www.jianshu.com/p/6d7de7a00b8d)

---

# Anaconda 常用命令

## 查看已安装的包

```shell
conda list  
```

## 更新所有包

```shell
conda upgrade --all  
```

## 安装包

```shell
conda install package_name  
```

## 删除包

```shell
conda remove package_name  
```

## 更新包

```shell
conda update package_name  
```

## 不知道包名要找包

```shell
conda search name  
```

---

# 虚拟环境

## 用conda建立

```shell
conda create -n env_name  list_of_packages
```

其中 -n 代表 name，env_name 是需要创建的环境名称，list of packages 则是列出在新环境中需要安装的工具包。例如，当我安装了 Python3 版本的 Anaconda 后，默认的 root 环境自然是 Python3，但是我还需要创建一个 Python 2 的环境来运行旧版本的 Python 代码，最好还安装了 pandas 包，于是我们运行以下命令来创建:  

```shell
conda create -n py2 python=2.7 pandas
```

细心的你一定会发现，py2 环境中不仅安装了 pandas，还安装了 numpy 等一系列 packages，这就是使用 conda 的方便之处，它会自动为你安装相应的依赖包，而不需要你一个个手动安装。

## 进入虚拟环境

```shell
source activate env_name
```

## 退出虚拟环境

```shell
source deactivate
```

## 删除名为 env_name 的环境

```shell
conda env remove -n env_name
```

## 显示所有的环境

```shell
conda env list
```

## 环境分享

当分享代码的时候，同时也需要将运行环境分享给大家，执行如下命令可以将当前环境下的 package 信息存入名为 environment 的 YAML 文件中

```shell
conda env export > environment.yaml
```

使用别人生成的yaml文件创建环境

```shell
conda env create -f environment.yaml
```

---

# anaconda换源

查看.condarc

```shell
conda config --show-sources
```

修改.condarc 位置从上面一步看 若找不到.condarc也可以先执行最后一步

```shell
sudo vim /home/username/.condarc

# 改为下面
channels:  
  - defaults  
show_channel_urls: true  
default_channels:  
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main  
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free  
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/r  
custom_channels:  
  conda-forge: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud  
  msys2: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud  
  bioconda: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud  
  menpo: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud  
  pytorch: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud  
  simpleitk: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud  
```

执行

```shell
conda config --set show_channel_urls yes
```
