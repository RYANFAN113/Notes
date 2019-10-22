- [修改 CentOS6 内核支持安装锐速](#%e4%bf%ae%e6%94%b9-centos6-%e5%86%85%e6%a0%b8%e6%94%af%e6%8c%81%e5%ae%89%e8%a3%85%e9%94%90%e9%80%9f)
- [锐速破解版](#%e9%94%90%e9%80%9f%e7%a0%b4%e8%a7%a3%e7%89%88)
- [自动一键安装SS](#%e8%87%aa%e5%8a%a8%e4%b8%80%e9%94%ae%e5%ae%89%e8%a3%85ss)

---

# 修改 CentOS6 内核支持安装锐速

首先运行下面命令为自己的VPS下载安装内核。

```shell
uname -r #查看当前内核版本
rpm -ivh http://backups.izchuan.com/kernel-firmware-2.6.32-504.3.3.el6.noarch.rpm  
rpm -ivh http://backups.izchuan.com/kernel-2.6.32-504.3.3.el6.x86_64.rpm --force
```

执行命令“rpm -qa | grep kernel”，查看内核是否安装成功。如果显示你安装的内核版本，表示安装成功。

```shell
rpm -qa | grep kernel
```

重启VPS，查看内核是否修改成功。

---

# 锐速破解版

安装

```shell
wget -N --no-check-certificate https://github.com/91yun/serverspeeder/raw/master/serverspeeder.sh && bash serverspeeder.sh
```

卸载

```shell
chattr -i /serverspeeder/etc/apx* && /serverspeeder/bin/serverSpeeder.sh uninstall -f
```

---

# 自动一键安装SS

```shell
wget --no-check-certificate -O shadowsocks.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks.sh
chmod +x shadowsocks.sh
./shadowsocks.sh 2>&1 | tee shadowsocks.log
```
