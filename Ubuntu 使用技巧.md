# 目录

- [目录](#%e7%9b%ae%e5%bd%95)
- [References](#references)
- [用命令行设置chrome的proxy](#%e7%94%a8%e5%91%bd%e4%bb%a4%e8%a1%8c%e8%ae%be%e7%bd%aechrome%e7%9a%84proxy)
- [使用alias自定义快捷命令](#%e4%bd%bf%e7%94%a8alias%e8%87%aa%e5%ae%9a%e4%b9%89%e5%bf%ab%e6%8d%b7%e5%91%bd%e4%bb%a4)
  - [打印当前所有别名设置情况](#%e6%89%93%e5%8d%b0%e5%bd%93%e5%89%8d%e6%89%80%e6%9c%89%e5%88%ab%e5%90%8d%e8%ae%be%e7%bd%ae%e6%83%85%e5%86%b5)
  - [临时别名](#%e4%b8%b4%e6%97%b6%e5%88%ab%e5%90%8d)
  - [永久别名](#%e6%b0%b8%e4%b9%85%e5%88%ab%e5%90%8d)

---

# References

[Linux系统中swap分区的设置与增加/删除](https://www.jb51.net/article/142928.htm)

[使用 AppImageLauncher 轻松运行和集成 AppImage 文件](https://cloud.tencent.com/developer/news/215568)

[Ubuntu使用alias自定义快捷命令](https://blog.csdn.net/weixin_40293491/article/details/81177423)

---

# 用命令行设置chrome的proxy

```shell
google-chrome-stable --proxy-server="socks5://127.0.0.1:1080"
```

---

# 使用alias自定义快捷命令

## 打印当前所有别名设置情况

```shell
alias -p
```

## 临时别名

```shell
alias newname_of_command='oldname_of_command'
```

## 永久别名

编辑 ~/.bashrc 文件

```shell
vim ~/.bashrc

# 将 alias newname_of_command='oldname_of_command 命令添加进去
```

注意：
等号前后不能有空格
