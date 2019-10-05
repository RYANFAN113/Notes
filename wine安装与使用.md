# 安装winehq
### If your system is 64 bit, enable 32 bit architecture (if you haven't already:
sudo dpkg --add-architecture i386 
### Download and add the repository key:
wget -nc https://dl.winehq.org/wine-builds/winehq.key  
sudo apt-key add winehq.key
### Add the repository:Ubuntu 18.04
sudo apt-add-repository 'deb https://dl.winehq.org/wine-builds/ubuntu/ bionic main'
### Update packages:
sudo apt update
### Then install one of the following packages:
sudo apt install --install-recommends winehq-stable

# 安装winetricks
sudo apt install winetricks

# 解决微信输入问题
winetricks riched20