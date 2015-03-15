#安装好Kali后为系统添加一个新用户,建议设置密码和root的一样,以后默认都用这个用户登录系统,需要执行一次性的高权限命令时用sudo,执行一系列高权限命令时用su -

useradd -m -G video,audio,cdrom,sudo -s /bin/bash 用户名 
passwd 用户名

#网络配置好了,接来下把系统更新到最新
apt-get update
apt-get upgrade

#安装输入法,个人习惯选择ibus,按自己的习惯安装输入法.重启后右键点击右上角的输入法图标->首选项->输入法+中文->高级(勾上所有程序共享使用同一个输入法).但是现在先不重启,重启后记得设置就行.
apt-get install ibus ibus-googlepinyin

#安装各种源里常用的软件,以下是我的习惯…
apt-get install gimp gedit emacs pidgin pidgin-otr iceweasel-l10n-zh-cn icedove icedove-l10n-zh-cn axel



cd /usr/share/
git clone https://github.com/rofl0r/proxychains-ng
cd proxychains-ng
./configure
make && make install
#修改~/.bashrc alias p='proxychains4 -q'