# 配置git
```angular2html
1.检测-是否安装git
git --version
若安装，则输出git版本号

2.在linux中安装git
sudo apt update
sudo apt install git

3.配置git
设置用户名和邮箱地址
3.1 运行以下命令来配置git全局用户名和邮箱
git config --global user.name "your name"
git config --global user.email "your_email@example.com"

3.2
你可以通过以下命令来检查配置是否成功：
git config --global --list
这将显示你设置的用户名和电子邮箱

3.3 
如果你发现配错了
要重置git的全局配置，可以使用以下命令
git config --global --unset-all user.name
git config --global --unset-all user.email
这将删除全局配置中的相应的键值对，重置后，git将不再使用这些值作为默认
的配置。

4.生成SSH密钥sudo apt update

若果你要使用git和远程仓库（如github）进行交互，建议生成SSH密钥并添加到
你的git账户中，这样，你可以避免每次推送代码时输入用户名和密码

生成SSH密钥：
ssh-keygen -t rsa -b 4096 -C "your-email@example.com"
直接enter三次
可以通过以下命令复制公钥
cat ~/.ssh/id_rsa.pub

将显示的公钥复制到github SSH密钥中
```

# 安装tar.gz
## 以pycharm为例
```angular2html
第一步：下载
压缩包下载好后可以在Downloads中找到,打开终端，进入downloads目录中
cd ~/Downloads
第二步：解压缩
用以下命令解压缩：
dingyong@HaJiMi:~/Downloads$ tar -zxvf pycharm-2025.2.1.1.tar.gz 
第三步：将文件移动到/usr/lib目录下
sudo mv pycharm-2025.2.1.1/ /usr/lib/
第四步：
进入/usr/lib/pycharm-2025.2.1.1/bin目录
运行 ./pycharm
第五步：
创建桌面快捷键
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