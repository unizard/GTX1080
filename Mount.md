


 ## HDD mount

 ls -l /dev/disk/by-uuid/
 sudo gedit /etc/fstab
 
 UUID=29f6905f-be40-4321-b7c0-7658f2cb4c3e       /srv/repository ext4    errors=remount-ro       0       1
 
 sudo mount -a
 df -h
