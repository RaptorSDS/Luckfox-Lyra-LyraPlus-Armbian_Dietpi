# Luckfox-Lyra-LyraPlus-Armbian_Dietpi
Luckfox Lyra LyraPlus Armbian (DEBIAN BOOKWORM) and Dietpi image with dual USB , USB Wifi include Firmware and Network manager


install -y git wget curl gnupg2 lsb-release \
  build-essential bc bison flex libssl-dev \
  libncurses5-dev libncursesw5-dev \
  fakeroot debootstrap qemu-user-static \
  device-tree-compiler python3 python3-setuptools python3-pkg-resources \
  dosfstools parted zip unzip rsync


____________________________________________________________________

cd ~
git clone https://github.com/armbian/build.git
cd build

_______________________________________________________________
./compile.sh
change kernel --> device driver -->Network --> USB-Network & Wifi-adapter--> selcet your needs
______________________________________________________

sudo nano /home/test/build/cache/sources/linux-kernel-worktree/6.1__rockchip__armhf/arch/arm/boot/dts/rk3506-luckfox-lyra.dtsi

change End of dtsi USB0 _otg to host

_________________________________________
./compile.sh build   BOARD=luckfox-lyra-plus   BRANCH=vendor   RELEASE=bookworm   BUILD_DESKTOP=no   BUILD_MINIMAL=yes   KERNEL_CONFIGURE=no  WIRELESS_EXTERNAL=no INSTALL_ARMBIAN_FIRMWARE=yes   INSTALL_FIRMWARE_ALL=yes   WIRELESS_UTILS="iw wireless-tools wpasupplicant"   NETWORKING_UTILS="network-manager nmtui"


_______________________________________________
when error i2c group already exist foloow
https://github.com/armbian/build/issues/9005
