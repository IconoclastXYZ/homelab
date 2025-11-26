## How to create an SMB share mounted inside a VM
Install CIFS and CIFS utils

Create directory for the mount 
mkdir /mnt/share

Set access to current user
sudo chmod 755 /mnt/share

create a credential file for the share
sudo nano .credentials

add the info
username=<username>
password=<password>

Set the ownership to root (for use with fstab) and reading to user only
sudo chown root .credentials
sudo chmod 600 .credentials

add entry to the /etc/fstab file
sudo nano /etc/fstab
add the line
//sourceIP/share /mnt/share cifs credentials=/home/user/.credentials,uid=1000,gid=1000,soft,nofail,x-systemd.automount,x-systemd.requires=network-online.target,_netdev 0 0
(as per https://stacygaudreau.com/blog/devops/smb-cifs-automount-on-linux-server/)

test with
sudo mount -a #mounts everything in the fstab file

unmount with
sudo umount -t cifs /mnt/share
