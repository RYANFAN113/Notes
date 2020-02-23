- [安装winehq](#%e5%ae%89%e8%a3%85winehq)
- [安装winetricks](#%e5%ae%89%e8%a3%85winetricks)
- [解决微信输入问题](#%e8%a7%a3%e5%86%b3%e5%be%ae%e4%bf%a1%e8%be%93%e5%85%a5%e9%97%ae%e9%a2%98)

---

# 安装winehq

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

为所需的libfaudio0库添加PPA

```shell
sudo add-apt-repository ppa:cybermax-dexter/sdl2-backport
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

# 安装winetricks

```shell
sudo apt install winetricks
```

---

# 解决微信输入问题

```shell
winetricks riched20
```
