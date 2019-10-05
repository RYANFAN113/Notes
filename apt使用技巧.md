# References
[原文转载](https://blog.csdn.net/u011596455/article/details/60322568)

[在Ubuntu中添加和删除PPA的软件源](https://blog.csdn.net/lu_embedded/article/details/55803500)

# apt强制停止后Could not get lock /var/lib/dpkg/lock解决方案
sudo rm /var/lib/dpkg/lock  
sudo rm /var/lib/apt/lists/lock  
sudo rm /var/cache/apt/archives/lock  

# 修改apt源
### 原文件备份
sudo cp /etc/apt/sources.list /etc/apt/sources.list.bak
### 编辑源列表文件
sudo vim /etc/apt/sources.list
### 将原来的列表删除，添加如下内容
### ##ustc sources
deb http://mirrors.ustc.edu.cn/ubuntu/ bionic main restricted universe multiverse  
deb http://mirrors.ustc.edu.cn/ubuntu/ bionic-security main restricted universe multiverse  
deb http://mirrors.ustc.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse  
deb http://mirrors.ustc.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse  
deb http://mirrors.ustc.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse  
#### # deb-src http://mirrors.ustc.edu.cn/ubuntu/ bionic main restricted universe multiverse  
#### # deb-src http://mirrors.ustc.edu.cn/ubuntu/ bionic-security main restricted universe multiverse  
#### # deb-src http://mirrors.ustc.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse  
#### # deb-src http://mirrors.ustc.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse  
#### # deb-src http://mirrors.ustc.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse  

### ##ali sources
deb http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse  
deb http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse  
deb http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse  
deb http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse  
deb http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse  
#### # deb-src http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse  
#### # deb-src http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse  
#### # deb-src http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse  
#### # deb-src http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse  
#### # deb-src http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse  

# 在Ubuntu中添加和删除PPA的软件源
## 添加 PPA 源
#### 添加 PPA 源的命令为：  
sudo add-apt-repository ppa:user/ppa-name  
#### 添加好记得要更新一下：  
sudo apt-get update
## 删除 PPA 源
#### 删除 PPA 源的命令格式则为：  
sudo add-apt-repository -r ppa:user/ppa-name  
#### 然后进入 /etc/apt/sources.list.d 目录，将相应 ppa 源的保存文件删除。
#### 最后同样更新一下：  
sudo apt-get update
