# wine 安装与使用

---

## 安装winehq

If your system is 64 bit, enable 32 bit architecture (if you haven't already:

```shell
sudo dpkg --add-architecture i386  
```

Download and add the repository key:  

```shell
wget -nc https://dl.winehq.org/wine-builds/winehq.key  
sudo apt-key add winehq.key
```

Add the repository:Ubuntu 18.04  

```shell
sudo apt-add-repository 'deb https://dl.winehq.org/wine-builds/ubuntu/ bionic main'
```

Update packages:  

```shell
sudo apt update
```

Then install one of the following packages:

```shell
sudo apt install --install-recommends winehq-stable
```

---

## 安装winetricks

```shell
sudo apt install winetricks
```

---

## 解决微信输入问题

```shell
winetricks riched20
```
