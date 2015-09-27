# VPS for FreeBSD 10.1-Release patch by spg

## How to use

### 1. build and install kernel  
on FreeBSD 10.1-Release
```shell
cd /usr/src
patch -p1 < spg-FreeBSD10.1-VPS.patch
```
Please build kernel.  
### 2. install binary
```shell
fetch http://www.7he.at/freebsd/vps/files/pkgs/vps-amd64-prod-r215.txz
tar xvf vps-amd64-prod-r215.txz
cp -r usr /
cp -r sbin /
cp -r etc /
```
### 3. rename file
```shell
mv /etc/defautls/devfs.rules /etc/defautls/devfs.rules_backup
reboot
```
If you don't rename `devfs.rules` file, vps instance can't mount devfs.  
Because boot time, executed default devfs rules. ( devfs_rules_ioctl() )
### 4. VPS instance setup
http://www.7he.at/freebsd/vps/docs/setup_testenv.txt

## base patch
http://www.7he.at/freebsd/vps/
