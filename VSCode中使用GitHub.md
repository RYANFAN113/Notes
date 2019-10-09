# 目录

- [目录](#%e7%9b%ae%e5%bd%95)
- [References](#references)
- [GIT 配置方法](#git-%e9%85%8d%e7%bd%ae%e6%96%b9%e6%b3%95)
  - [下载Git并安装，并添加路径到环境变量](#%e4%b8%8b%e8%bd%bdgit%e5%b9%b6%e5%ae%89%e8%a3%85%e5%b9%b6%e6%b7%bb%e5%8a%a0%e8%b7%af%e5%be%84%e5%88%b0%e7%8e%af%e5%a2%83%e5%8f%98%e9%87%8f)
  - [在GitHub上新建一个仓库](#%e5%9c%a8github%e4%b8%8a%e6%96%b0%e5%bb%ba%e4%b8%80%e4%b8%aa%e4%bb%93%e5%ba%93)
  - [在本地新建一个文件夹，作为VSCode代码的工作文件夹](#%e5%9c%a8%e6%9c%ac%e5%9c%b0%e6%96%b0%e5%bb%ba%e4%b8%80%e4%b8%aa%e6%96%87%e4%bb%b6%e5%a4%b9%e4%bd%9c%e4%b8%bavscode%e4%bb%a3%e7%a0%81%e7%9a%84%e5%b7%a5%e4%bd%9c%e6%96%87%e4%bb%b6%e5%a4%b9)
  - [在命令行方式下进入mycode，输入](#%e5%9c%a8%e5%91%bd%e4%bb%a4%e8%a1%8c%e6%96%b9%e5%bc%8f%e4%b8%8b%e8%bf%9b%e5%85%a5mycode%e8%be%93%e5%85%a5)
  - [添加用户名和邮箱。该用户名和邮箱是注册GitHub时使用的用户名和邮箱](#%e6%b7%bb%e5%8a%a0%e7%94%a8%e6%88%b7%e5%90%8d%e5%92%8c%e9%82%ae%e7%ae%b1%e8%af%a5%e7%94%a8%e6%88%b7%e5%90%8d%e5%92%8c%e9%82%ae%e7%ae%b1%e6%98%af%e6%b3%a8%e5%86%8cgithub%e6%97%b6%e4%bd%bf%e7%94%a8%e7%9a%84%e7%94%a8%e6%88%b7%e5%90%8d%e5%92%8c%e9%82%ae%e7%ae%b1)
  - [生成秘钥。继续在该目录下输入](#%e7%94%9f%e6%88%90%e7%a7%98%e9%92%a5%e7%bb%a7%e7%bb%ad%e5%9c%a8%e8%af%a5%e7%9b%ae%e5%bd%95%e4%b8%8b%e8%be%93%e5%85%a5)
  - [绑定本地文件夹和GitHub仓库](#%e7%bb%91%e5%ae%9a%e6%9c%ac%e5%9c%b0%e6%96%87%e4%bb%b6%e5%a4%b9%e5%92%8cgithub%e4%bb%93%e5%ba%93)
  - [先进行一次拉取，再进行一次推送](#%e5%85%88%e8%bf%9b%e8%a1%8c%e4%b8%80%e6%ac%a1%e6%8b%89%e5%8f%96%e5%86%8d%e8%bf%9b%e8%a1%8c%e4%b8%80%e6%ac%a1%e6%8e%a8%e9%80%81)
- [VSCode 配置方法](#vscode-%e9%85%8d%e7%bd%ae%e6%96%b9%e6%b3%95)

---

# References

[VSCode中使用GitHub](https://blog.csdn.net/piglite/article/details/88222695)

---

# GIT 配置方法

## 下载Git并安装，并添加路径到环境变量  

```shell
git --version  
# 如果显示版本号，则安装成功  
```

## 在GitHub上新建一个仓库

例如：mycode

## 在本地新建一个文件夹，作为VSCode代码的工作文件夹

例如：mycode  
mycode既是VSCode的代码工作文件夹又应该是Git的本地仓库。

## 在命令行方式下进入mycode，输入

```shell
git init
```

## 添加用户名和邮箱。该用户名和邮箱是注册GitHub时使用的用户名和邮箱

```shell
git config --global user.name "myname"  
git config --global user.email "myname@mymail.com"
```

## 生成秘钥。继续在该目录下输入

```shell
ssh-keygen -t rsa -C "myname@mymail.com"  
# 命令执行完毕会生成一个名为id_rsa.pub的文件。利用文本编辑器打开该文件，全文复制  
# 打开GitHub上的myrepo仓库，进入setting，设置deploy keys，将id_rsa.pub中的内容粘贴进去即可。默认会生成该key对应的title为myname@mymail.com
```

## 绑定本地文件夹和GitHub仓库

```shell
git remote add mycode git@github.com:myname/myrepo.git

# 设置完成后可以做一下连接测试：
ssh -T git@github.com
```

## 先进行一次拉取，再进行一次推送

```shell
git pull mycode master  
git push --force mycode master
```

---

# VSCode 配置方法

上述配置都进行完成后，就可以利用VSCode打开mycode文件夹进行相关操作。此时任何在该文件夹下出现的改变，VSCode的“源代码管理”图标上都会出现相应发生改变的文件的数字。点击“源代码管理”图片后，会列出来所有发生改变的文件名称，点击右上角的...，进行“提交”操作。

提交完毕后检查GitHub的myrepo会发生相应的变化。如果没有变化，在VSCode中打开控制台（ctrl+`）选择“输出”，看是否有相关的错误提示，根据错误提示信息进行调整。
