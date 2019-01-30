# openwrt-3.10.14

sudo apt-get install libncurses5-dev zlib1g-dev gawk flex patch git-core g++ subversion //安装编译依赖

./scripts/feeds update -a  //更新软件包

./scripts/feeds install -a //安装更新包

cp config_7620 .config     //将当前config_7620配置文件拷贝 .config

make menuconfig 	   //配置软件包

make kernel_menuconfig	   //配置kernel

make V=s   		   //编译

可能出现错误

一、ERROR: module 'build_dir/target-mipsel_24kec+dsp_uClibc-0.9.33.2/linux-ramips_mt7620/linux-3.10.14-p112871/sound/core/snd-compress.ko' is missing.

修改build_dir/target-mipsel_24kec+dsp_uClibc-0.9.33.2/linux-ramips_mt7620/linux-kernel/sound/core/Makefile 文件

#obj-$(CONFIG_SND_COMPRESS_OFFLOAD)     += snd-compress.o

obj-m   += snd-compress.o

二、fatal error: iconv.h: No such file or directory

cd staging_dir/target-mipsel_24kec+dsp_uClibc-0.9.33.2/usr/lib/libiconv-full

cp include/iconv.h  ../../include/

cp lib/libiconv.a  ../../lib/ -frd

不用复制 libiconv.so*

PPTP问题

修改 build_dir/target-mipsel_24kec+dsp_uClibc-0.9.33.2/linux-ramips_mt7620/linux-kernel/drivers/net/ppp/Kconfig +133

config PPTP

#config PPPOPPTP

生成固件目录

bin/ramips/openwrt-ramips-mt7620-mt7620-squashfs-sysupgrade.bin

git add . -A 

git commit -m "first commit"

git push -u origin master

