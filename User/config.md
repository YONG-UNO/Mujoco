# 安装tar.gz
## 以pycharm为例
```angular2html
压缩包下载好后可以在Downloads中找到
```

# 安装显卡驱动
```angular2html
ubuntu-driver devices
列出推荐的驱动
sudo apt-get install nvidia-driver-575-open
或者
sudo ubuntu-drivers autoinstall
自动安装recommend驱动
最后
sudo reboot
```

# 卸载firefox
```angular2html
使用apt-get命令删除
sudo apt-get purge firefox
purge命令会删除软件包及其所有配置文件
```
```angular2html
卸载firefox后，系统中仍存在一些残留文件和文件夹，以下是一些常见清理步骤：
1.清理用户目录下的残留文件
Firefox的个人数据存储在~/.mozilla文件夹中。可以通过以下命令删除该文件夹：
rm -rf ~/.mozilla

注意：此操作会删除所有Firefox的个人数据，包括书签、密码等。如果你之前进行了备份，可以忽略此步骤。

2. 清理系统缓存
使用以下命令清理系统的软件包缓存：

sudo apt-get autoclean
sudo apt-get clean
sudo apt-get autoremove
3. 清理孤立的软件包
可以使用gtkorphan或deborphan工具来查找和删除孤立的软件包：

sudo apt-get install gtkorphan -y
sudo gtkorphan
```