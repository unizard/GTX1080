

# [xrdp & mate] 

$ sudo apt-get update <br />
$ sudo apt-get install xrdp <br />
$ sudo apt-add-repository ppa:ubuntu-mate-dev/ppa <br />
$ sudo apt-add-repository ppa:ubuntu-mate-dev/trusty-mate <br />
$ sudo apt-get update <br />
$ sudo apt-get upgrade <br />
$ sudo apt-get install ubuntu-mate-core ubuntu-mate-desktop <br />
$ echo mate-session > ~/.xsession <br />
$ sudo service xrdp restart <br />


``` 
#!/bin/sh 
if [ -r /etc/default/locale ]; then 
  . /etc/default/locale 
  export LANG LANGUAGE 
fi 

 mate-session <- 반드시 추가 
```

$ sudo service xrdp restart <br />


# [xrdp & xfce4] 

$ sudo apt-get update <br />
$ sudo apt-get install xrdp <br />
$ sudo apt-get install xfce4 <br />
$ echo xfce4-session >~/.xsession <br />
$ sudo gedit /etc/xrdp/startwm.sh <br />

```
#!/bin/sh 
if [ -r /etc/default/locale ]; then 
  . /etc/default/locale 
  export LANG LANGUAGE 
fi 
startxfce4 
```
$ sudo service xrdp restart <br />



# xrdp login setting

$ sudo gedit /etc/xrdp/xrdp.ini 

```
[xrdp1] 
name=sesman-Xvnc 
lib=libvnc.so 
username=ask 
passwod=ask 
ip=127.0.0.1 
port=ask-1 
```

port=ask 라고 하면 매번 접속시에 포트번호를 물어보고 
-1로 한 이유는 새로운 세션을 생성하기 위한거고 
고정하고 싶으면 고정하고;;




# xrdp issues
http://aloftcat.tistory.com/88 



