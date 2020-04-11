# Installation on Ubuntu

<https://www.universalmediaserver.com/>
<https://github.com/UniversalMediaServer/UniversalMediaServer/wiki/Linux-install-instructions>
<https://steamforge.net/wiki/index.php/How_to_setup_Universal_Media_Server_8.0.1_under_Ubuntu_18.04>
<https://nerdpause.de/ums-als-systemd-service/>

## Install tsMuxeR dependencies (32-bit)

```bash
sudo dpkg --add-architecture i386
sudo apt update
sudo apt install -y \
lib32z1 \
lib32ncurses5 \
libbz2-1.0:i386 \
libstdc++6:i386
```

## Install other dependencies

```bash
sudo apt install -y \
openjdk-8-jre \
mediainfo \
dcraw \
vlc \
unzip \
p7zip
```

## Download UMS

```bash
UMS_VERSION="9.2.0"
wget https://sourceforge.net/projects/unimediaserver/files/Official%20Releases/Linux/UMS-${UMS_VERSION}.tgz/download -O ums.tgz
tar xzvf ums.tgz
```

## Install UMS

```bash
mv ums-${UMS_VERSION} /opt/UMS
cd /opt/UMS
./UMS.sh
```
