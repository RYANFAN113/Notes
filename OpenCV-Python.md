# 安装
pip3 install opencv-python
# 缺少共享文件库
# 安装apt-file
sudo apt install apt-file
# 使用apt-file查找依赖
apt-file search libSM.so.6
# 根据提示安装合适的依赖库
apt-get install libsm6