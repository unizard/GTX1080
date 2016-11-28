

=============================== 
xrdp 각종 문제 해결 모음 
=============================== 

http://aloftcat.tistory.com/88 



[원격설정 - mate] 

$ sudo apt-add-repository ppa:ubuntu-mate-dev/ppa 
$ sudo apt-add-repository ppa:ubuntu-mate-dev/trusty-mate 
$ sudo apt-get update 
$ sudo apt-get upgrade 
$ sudo apt-get install ubuntu-mate-core ubuntu-mate-desktop 
$ echo mate-session > ~/.xsession 
$ sudo service xrdp restart 

======================================= 

``` 
#!/bin/sh 
if [ -r /etc/default/locale ]; then 
  . /etc/default/locale 
  export LANG LANGUAGE 
fi 

 mate-session <- 반드시 추가 
```
======================================= 
sudo service xrdp restart

관리자 16-11-19 20:13 답변  
[원격설정 - xfce4] 

sudo apt-get update 
sudo apt-get install xrdp 
sudo apt-get install xfce4 
echo xfce4-session >~/.xsession 
sudo nano /etc/xrdp/startwm.sh 

======================================= 
```
#!/bin/sh 
if [ -r /etc/default/locale ]; then 
  . /etc/default/locale 
  export LANG LANGUAGE 
fi 
startxfce4 
```
======================================= 
sudo service xrdp restart






=================== 
xrdp 로그인 환경설정 
=================== 

sudo gedit /etc/xrdp/xrdp.ini 

[xrdp1] 
name=sesman-Xvnc 
lib=libvnc.so 
username=ask 
passwod=ask 
ip=127.0.0.1 
port=ask-1 


port=ask 라고 하면 매번 접속시에 포트번호를 물어보고 
-1로 한 이유는 새로운 세션을 생성하기 위한거고 
고정하고 싶으면 고정하고;;





