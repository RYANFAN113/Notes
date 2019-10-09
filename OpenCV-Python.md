# 目录

- [目录](#%e7%9b%ae%e5%bd%95)
- [安装](#%e5%ae%89%e8%a3%85)
- [缺少共享文件库](#%e7%bc%ba%e5%b0%91%e5%85%b1%e4%ba%ab%e6%96%87%e4%bb%b6%e5%ba%93)

---

# 安装

```shell
pip3 install opencv-python
```

---

# 缺少共享文件库

安装apt-file  

```shell
sudo apt install apt-file
```

使用apt-file查找依赖

```shell
apt-file search libSM.so.6
```

根据提示安装合适的依赖库

```shell
apt-get install libsm6
```
