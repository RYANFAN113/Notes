- [References](#references)
- [docker 常用命令](#docker-%e5%b8%b8%e7%94%a8%e5%91%bd%e4%bb%a4)
  - [部署　docker 容器](#%e9%83%a8%e7%bd%b2-docker-%e5%ae%b9%e5%99%a8)
  - [重命名容器名](#%e9%87%8d%e5%91%bd%e5%90%8d%e5%ae%b9%e5%99%a8%e5%90%8d)
  - [删除镜像](#%e5%88%a0%e9%99%a4%e9%95%9c%e5%83%8f)
  - [删除容器](#%e5%88%a0%e9%99%a4%e5%ae%b9%e5%99%a8)
- [docker 设置 jupyter notebook](#docker-%e8%ae%be%e7%bd%ae-jupyter-notebook)
- [后台运行jupyter](#%e5%90%8e%e5%8f%b0%e8%bf%90%e8%a1%8cjupyter)

---

# References

[docker环境使用tensorflow以及jupyter notebook的使用](https://blog.csdn.net/qq_16949707/article/details/64497701)

[玩转Jupyter Notebook](https://cloud.tencent.com/developer/article/1147487)

---

# docker 常用命令

## 部署　docker 容器

```shell
sudo docker run -p hostport:8888 -it -v /host:/server image
```

## 重命名容器名

```shell
docker rename 原容器名  新容器名
```

## 删除镜像

```shell
docker rmi <image id>
```

## 删除容器

```shell
docker rm <container id>
```

---

# docker 设置 jupyter notebook

设置密码 保存sha1密匙（带‘’）  

```shell
python  
from notebook.auth import passwd  
passwd()
```

生成配置文件  

```shell
jupyter notebook --generate-config
```

修改配置文件  

```shell
vim ~/.jupyter/jupyter_notebook_config.py

#修改为  
c.NotebookApp.ip='*'  
c.NotebookApp.password = u'sha1:d49a3bff8995:f6899083acc0d705aefcf3864c8eb3ac20ed258c'  
c.NotebookApp.open_browser = False  
c.NotebookApp.port =8888  
```

手动添加kernel  

```shell
python -m ipykernel install --name tensorflow --display-name "tensorflow(python3.6)"
```

---

# 后台运行jupyter  

```shell
nohup jupyter notebook > /data/jupyter/jupyter.log 2>&1 --ip=0.0.0.0 &
```
