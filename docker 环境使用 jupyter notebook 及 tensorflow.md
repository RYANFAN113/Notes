# docker环境使用tensorflow以及jupyter notebook的使用
[docker环境使用tensorflow以及jupyter notebook的使用](https://blog.csdn.net/qq_16949707/article/details/64497701)

[玩转Jupyter Notebook](https://cloud.tencent.com/developer/article/1147487)

sudo docker run -p 7777:8888 -it -v /home/host:/home/server image

# docker 设置 jupyter notebook
## 设置密码 保存sha1密匙（带‘’）
python  
from notebook.auth import passwd  
passwd()
## 生成配置文件
jupyter notebook --generate-config
## 修改配置文件
vim ~/.jupyter/jupyter_notebook_config.py
#### 修改为
c.NotebookApp.ip='*'  
c.NotebookApp.password = u'sha1:d49a3bff8995:f6899083acc0d705aefcf3864c8eb3ac20ed258c'  
c.NotebookApp.open_browser = False  
c.NotebookApp.port =8888  

# 手动添加kernel
python -m ipykernel install --name tensorflow --display-name "tensorflow(python3.6)"

# 后台运行jupyter
nohup jupyter notebook > /data/jupyter/jupyter.log 2>&1 --ip=0.0.0.0 &