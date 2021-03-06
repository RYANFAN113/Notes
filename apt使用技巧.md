- [References](#references)
- [修改apt源](#%e4%bf%ae%e6%94%b9apt%e6%ba%90)
  - [原文件备份](#%e5%8e%9f%e6%96%87%e4%bb%b6%e5%a4%87%e4%bb%bd)
  - [编辑源列表文件](#%e7%bc%96%e8%be%91%e6%ba%90%e5%88%97%e8%a1%a8%e6%96%87%e4%bb%b6)
- [在Ubuntu中添加和删除PPA的软件源](#%e5%9c%a8ubuntu%e4%b8%ad%e6%b7%bb%e5%8a%a0%e5%92%8c%e5%88%a0%e9%99%a4ppa%e7%9a%84%e8%bd%af%e4%bb%b6%e6%ba%90)
  - [添加 PPA 源](#%e6%b7%bb%e5%8a%a0-ppa-%e6%ba%90)
  - [删除 PPA 源](#%e5%88%a0%e9%99%a4-ppa-%e6%ba%90)
- [Error](#error)
  - [N: Skipping acquire of configured file 'universe/binary-i386/Packages' as repository '<http://miktex.org/download/ubuntu>' bionic InRelease' doesn't support architecture 'i386'](#n-skipping-acquire-of-configured-file-universebinary-i386packages-as-repository-httpmiktexorgdownloadubuntu-bionic-inrelease-doesnt-support-architecture-i386)
  - [error: Could not get lock /var/lib/dpkg/lock](#error-could-not-get-lock-varlibdpkglock)
  - [error: dpkg frontend is locked by another process](#error-dpkg-frontend-is-locked-by-another-process)
  - [error: <http://mirrors.aliyun.com/ubuntu> bionic-security InRelease The following signatures couldn't be verified because the public key is not available: NO_PUBKEY 3B4FE6ACC0B21F32](#error-httpmirrorsaliyuncomubuntu-bionic-security-inrelease-the-following-signatures-couldnt-be-verified-because-the-public-key-is-not-available-nopubkey-3b4fe6acc0b21f32)
  
---

# References

[原文转载](https://blog.csdn.net/u011596455/article/details/60322568)

[在Ubuntu中添加和删除PPA的软件源](https://blog.csdn.net/lu_embedded/article/details/55803500)

---

# 修改apt源

## 原文件备份

```shell
sudo cp /etc/apt/sources.list /etc/apt/sources.list.bak
```

## 编辑源列表文件

```shell
sudo vim /etc/apt/sources.list

# 将原来的列表删除，添加如下内容:

# ustc sources  
deb http://mirrors.ustc.edu.cn/ubuntu/  bionic main restricted universe multiverse  
deb http://mirrors.ustc.edu.cn/ubuntu/ bionic-security main restricted universe multiverse  
deb http://mirrors.ustc.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse  
deb http://mirrors.ustc.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse  
deb http://mirrors.ustc.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse  
# deb-src http://mirrors.ustc.edu.cn/ubuntu bionic main restricted universe multiverse  
# deb-src <http://mirrors.ustc.edu.cn/ubuntu/ bionic-security main restricted universe multiverse  
# deb-src http://mirrors.ustc.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse  
# deb-src http://mirrors.ustc.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse  
# deb-src http://mirrors.ustc.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse  

# ali sources
deb http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse  
deb http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse  
deb http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse  
deb http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse  
deb http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse  
# deb-src http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse  
# deb-src http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse  
# deb-src http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse  
# deb-src http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse  
# deb-src http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse  
```

---

# 在Ubuntu中添加和删除PPA的软件源

## 添加 PPA 源

添加 PPA 源的命令

```shell
sudo add-apt-repository ppa:user/ppa-name  
```

添加好记得要更新一下

```shell
sudo apt-get update
```

## 删除 PPA 源

删除 PPA 源的命令格式则为

```shell
sudo add-apt-repository -r ppa:user/ppa-name
```

然后进入 /etc/apt/sources.list.d 目录，将相应 ppa 源的保存文件删除。
最后同样更新一下：

```shell
sudo apt-get update
```

---

# Error

## N: Skipping acquire of configured file 'universe/binary-i386/Packages' as repository '<http://miktex.org/download/ubuntu>' bionic InRelease' doesn't support architecture 'i386'

```shell
sudo vim /etc/apt/sources.list.d/miktex.list

# 在deb后面加入 [arch=amd64]
```

## error: Could not get lock /var/lib/dpkg/lock

```shell
sudo rm /var/lib/dpkg/lock  
sudo rm /var/lib/apt/lists/lock  
sudo rm /var/cache/apt/archives/lock  
```

## error: dpkg frontend is locked by another process

```shell
sudo rm /var/lib/dpkg/lock
sudo rm /var/lib/dpkg/lock-frontend
sudo rm /var/cache/apt/archives/lock
```

## error: <http://mirrors.aliyun.com/ubuntu> bionic-security InRelease  The following signatures couldn't be verified because the public key is not available: NO_PUBKEY 3B4FE6ACC0B21F32

```shell
apt-key adv –keyserver keyserver.ubuntu.com –recv-keys 3B4FE6ACC0B21F32
```
