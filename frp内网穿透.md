下载 [frp](https://github.com/fatedier/frp/releases/tag/v0.40.0)
 
# 外网服务器端

删除客户端相关内容，仅保留服务端内容

```bash
cd /frp_0.37.1_linux_amd64
rm -f frpc*
```

配置服务器
frps.ini

```ini
[common]
bind_port = 7000

token = Ryan123456789

dashboard_port = 7500
dashboard_user = RYAN_FRP
dashboard_pwd = Ryan123456
enable_prometheus = true

log_file = /var/log/frps.log
log_level = info
log_max_days = 3
```

启动命令

```bash
mkdir -p /etc/frp
cp frps.ini /etc/frp
cp frps /usr/bin
cp systemd/frps.service /usr/lib/systemd/system/
systemctl enable frps
systemctl start frps
```

# 内网服务器客户端

删除服务器端相关内容，仅保留客户端内容

```bash
cd /frp_0.37.1_linux_amd64
rm -f frps*
```

配置客户端
frpc.ini

```ini
[common]
server_addr = 104.168.243.220
server_port = 7000
token = Ryan123456789
[gitea_ssh]
type = tcp
local_ip = 127.0.0.1
local_port = 8022
remote_port = 6000
[gitea_http]
type = tcp
local_ip = 127.0.0.1
local_port = 8088
remote_port = 6001
```

在PowerShell中运行

```PowerShell
.\frpc.exe -c .\frpc.ini
```

# 使用端

更改 ssh host
~/.ssh/config

```config
Host gitea    
    user git
    hostname 192.168.3.2
    port 8022

Host gitea_frp
    user git
    hostname 104.168.243.220
    port 6000
```

使用 git

```bash
git  clone gitea_frp:RYAN/*******.git
```