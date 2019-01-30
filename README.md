# openwrt-3.10.14

git init
git add * -fA
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/caiweiqing1990/openwrt-3.10.14.git
git push -u origin master

sudo apt-get install libncurses5-dev zlib1g-dev gawk flex patch git-core g++ subversion

./scripts/feeds update -a  //更新软件包

./scripts/feeds install -a //安装更新包

cp config_7620 .config     //将当前config_7620配置文件拷贝 .config

make menuconfig 	   //配置软件包

make kernel_menuconfig	   //配置kernel

make V=s   		   //编译

