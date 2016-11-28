

# ssh 
### installation & port change <br />

$ sudo apt-get install openssh-server <br />
$ gedit /etc/ssh/sshd_config  <br />
$ sudo gedit /etc/ssh/sshd_config  <br />

```
..
#port 22 
port 1024 
..
```

<br />
<br />


# sshfs
// Assume that ssh is already installed. <br />

### lock
$ sudo apt-get install sshfs <br />
$ sshfs -p 1024 user01@143.248.39.117:/data2/ ~/works_177   <br />
( port 2014, login id : user01 ) <br />

### unlock
$ fusermount -u ./works_177 <br />


<br />
<br />

# samba
### sharing files between window and linux

 $ sudo apt-get install samba <br />
 $ sudo smbpasswd -a user01 <br />
 $ sudo gedit /etc/samba/smb.conf  <br />

```
.. 
 [user01] 
 comment = user01 
 valid user = user01 
 path = /home/user01 
 browsable = yes  
 writable = yes 
```

$ sudo service smbd restart <br />


### softlink

$  sudo vi /etc/samba/smb.conf <br />

```
[global]

follow symlinks = yes
wide links = yes
unix extensions = no
```

$ sudo /etc/init.d/smbd restart <br />

### more detail
[link](http://storycompiler.tistory.com/31)

<br />

# sticky note 
$ sudo add-apt-repository ppa:umang/indicator-stickynotes <br/>
$ sudo apt-get update <br/>
$ sudo apt-get install indicator-stickynotes <br/>

<br />
<br /> 


# xpad
$ sudo apt-get install xpad <br/>
