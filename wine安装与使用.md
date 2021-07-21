- [安装winehq](#%e5%ae%89%e8%a3%85winehq)
- [安装winetricks](#%e5%ae%89%e8%a3%85winetricks)
- [解决微信输入问题](#%e8%a7%a3%e5%86%b3%e5%be%ae%e4%bf%a1%e8%be%93%e5%85%a5%e9%97%ae%e9%a2%98)
- [wine中文乱码的终极解决方法](#wine%e4%b8%ad%e6%96%87%e4%b9%b1%e7%a0%81%e7%9a%84%e7%bb%88%e6%9e%81%e8%a7%a3%e5%86%b3%e6%96%b9%e6%b3%95)

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

---

# wine中文乱码的终极解决方法

步骤：

1.初始设置

运行 winecfg，把模拟的 Windows 系统设置为 Windows XP 或者 Windows 2000。

2.准备字体

为了让 Windows 应用程序看上去更美观，所以需要 Windows 下面的字体。

由于我已经将 simsun.ttc 复制到 /usr/share/fonts/windows/ 目录中了。所以我只需要在 ~/.wine/drive_c/windows/fonts/ 目录中为 simsun.ttc 创建一个符号连接：

```bash
cd ~/.wine/drive_c/windows/fonts
ln -s /usr/share/fonts/windows/simsun.ttc simsun.ttc
ln -s /usr/share/fonts/windows/simsun.ttc simfang.ttc
```

创建一个 simfang.ttc 是许多 Windows 应用默认使用 simfang.ttc 字体。

3.修改 ~/.wine/system.reg

装好字体后，还要修改一下 Wine 的注册表设置，指定与字体相关的设置：

```bash
vim ~/.wine/system.reg
```

（一定要使用支持 gb2312/utf8 编码的编辑器修改这些文件，否则文件中的中文可能变乱码）

搜索： LogPixels
找到的行应该是：[System\\CurrentControlSet\\Hardware Profiles\\Current\\Software\\Fonts]
将其中的：

```bash
"LogPixels"=dword:00000060
```

改为：

```bash
"LogPixels"=dword:00000070
```

搜索： FontSubstitutes
找到的行应该是：[Software\\Microsoft\\Windows NT\\CurrentVersion\\FontSubstitutes]
将其中的：

```bash
"MS Shell Dlg"="Tahoma"
"MS Shell Dlg 2″="Tahoma"
```

改为：

```bash
"MS Shell Dlg"="SimSun"
"MS Shell Dlg 2″="SimSun"
```

4.修改 ~/.wine/drive_c/windows/win.ini

```bash
vim ~/.wine/drive_c/windows/win.ini
在文件末尾加入：
```

```bash
[Desktop]
menufontsize=13
messagefontsize=13
statusfontsize=13
IconTitleSize=13
```

5.最关键的一步，网上很多文章中没有提到的一步──把下面的代码保存为zh.reg，然后终端执行
```bash
sudo wine regedit zh.reg
```
从Windows目录下的Fonts里的simsun.ttc复制到/home/user/.wine/drive_c/windows/fonts里面。
代码:

```bash
REGEDIT4

[HKEY_LOCAL_MACHINE\Software\Microsoft\Windows NT\CurrentVersion\FontSubstitutes]
"Arial"="simsun"
"Arial CE,238"="simsun"
"Arial CYR,204"="simsun"
"Arial Greek,161"="simsun"
"Arial TUR,162"="simsun"
"Courier New"="simsun"
"Courier New CE,238"="simsun"
"Courier New CYR,204"="simsun"
"Courier New Greek,161"="simsun"
"Courier New TUR,162"="simsun"
"FixedSys"="simsun"
"Helv"="simsun"
"Helvetica"="simsun"
"MS Sans Serif"="simsun"
"MS Shell Dlg"="simsun"
"MS Shell Dlg 2"="simsun"
"System"="simsun"
"Tahoma"="simsun"
"Times"="simsun"
"Times New Roman CE,238"="simsun"
"Times New Roman CYR,204"="simsun"
"Times New Roman Greek,161"="simsun"
"Times New Roman TUR,162"="simsun"
"Tms Rmn"="simsun"
```

之后，中文正常显示
