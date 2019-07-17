### Emby Server

參考網址 https://hub.docker.com/r/emby/embyserver
```
docker pull emby/embyserver

docker run -it -d -v /c/:/myhome --net=host 8b6f
```
http://192.168.99.100:8096

![](https://github.com/a121514191/linux_media/blob/master/emby.PNG)

docker rm -f $(docker ps -aq) 刪除換下一個

### YouTransfer

參考網址https://hub.docker.com/r/remie/youtransfer
```
docker pull remie/youtransfer

docker run -it -d -v /c/:/myhome --net=host b9a7
```
http://192.168.99.100:5000

![](https://github.com/a121514191/linux_media/blob/master/youtransfer.PNG)

docker rm -f $(docker ps -aq) 刪除換下一個

### ProjectSend

參考網址 https://hub.docker.com/r/linuxserver/projectsend
```
docker pull linuxserver/projectsend

docker run -it -d -v /c/:/myhome --net=host 7e1b
```
http://192.168.99.100

![](https://github.com/a121514191/linux_media/blob/master/project.PNG)

docker rm -f $(docker ps -aq) 刪除換下一個

### Plex Media Server
step1 先建立好centos的container

```
docker pull centos

docker run -p 80:80 -d --privileged=true centos

docker exec -it centos bash

yum update
```
之後按照參考網址安裝

https://www.howtoing.com/centos-plex-media-server

都完成後打包成image檔

```
docker ps -a 

docker commit (id) (命名)

docker images

docker run -d --privileged=true -v /c/:/myhome --net=host plex
```
![](https://github.com/a121514191/linux_media/blob/master/plexmedia.PNG)

### 實作
