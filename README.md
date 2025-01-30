# Onecloud-can-do
 玩客云能部属的服务集合

###### apt 一键换源脚本 

```
bash <(curl -sSL https://linuxmirrors.cn/main.sh)
```

###### docker 安装脚本

```
curl -fsSL https://get.docker.com | bash -s docker
```

###### docker 一键换源脚本

```
bash <(curl -sSL https://linuxmirrors.cn/docker.sh)
```

###### git 一键换源脚本

这个大概有24小时的延迟(即内容是昨天的)

```
git config --global url."https://kgithub.com/" .insteadOf "https://github.com/"
```

###### alist

```
docker run -d --restart=always -v /etc/alist:/opt/alist/data -p 5244:5244 -e PUID=0 -e PGID=0 -e UMASK=022 --name=alist xhofe/alist-aria2:latest
```

###### CasaOS

```
curl -fsSL https://get.casaos.io | sudo bash
```

###### 1panel

```
curl -sSL https://resource.fit2cloud.com/1panel/package/quick_start.sh -o quick_start.sh && sudo bash quick_start.sh
```

###### Sun-Panel

```
docker pull hslr/sun-panel
docker run -d --restart=always -p 3002:3002 
-v ~/docker_data/sun-panel/conf:/app/conf 
--name sun-panel 
hslr/sun-panel:latest
```

###### typecho

```
mkdir /root/tyepcho
docker run -d --restart=always -p 80:80 --name typecho -v "/root/tyepcho":/var/www/html yangxuan8282/typecho:php-arm
```

###### aria

```
docker run -d \
    --name aria2-pro \
    --restart unless-stopped \
    --log-opt max-size=1m \
    --network host \
    -e PUID=$UID \
    -e PGID=$GID \
    -e RPC_SECRET=12345 \
    -e RPC_PORT=6800 \
    -e LISTEN_PORT=6888 \
    -v ~/aria2-config:/config \
    -v /home/powersee:/downloads \
    p3terx/aria2-pro
```

###### AriaNG

```
docker pull p3terx/ariang

docker run -d \
--name ariang \
--log-opt max-size=1m \
--restart unless-stopped \
-p 16880:6880 \
p3terx/ariang
```

###### Openwrt

请看这个网址：

```
https://www.jianshu.com/p/ab86fd279942#_Toc25995
```

###### MC服务器

请看这个网址：

```
https://github.com/Lirzh/Onecloud-MCServer
```

###### Zerotier

```
#安装
docker run --device=/dev/net/tun --name zerotier --net=host --restart=always --cap-add=NET_ADMIN --cap-add=SYS_ADMIN -v /var/lib/zerotier:/var/lib/zerotier zerotier/zerotier:latest
```

```
#加入组织网络；
docker exec zerotier zerotier-cli join <your-net-id>
#退出组织网络
docker exec zerotier zerotier-cli leave <your-net-id>
```

###### 微力同步

```
curl http://www.verysync.com/shell/verysync-linux-installer/go-installer.sh > go-installer.sh
chmod +x go-installer.sh
./go-installer.sh
```

###### DDNSTO

```
docker run -d --name=ddnsto --restart always --network host -e TOKEN=<自己的token> -e DEVICE_IDX=0 linkease/ddnsto:3.0.0
```

 (注意替换自己的token)

###### Verysync

```
back_path=/mnt/verysync
docker run -d \
--restart=unless-stopped \
--name verysync \
-v $back_path:/data \
-p 8886:8886 \
unwenliu/verysync:armv7
```

###### transmission

```
docker run \
    -d \
    --name transmission \
    -p 9091:9091 \
    -p 51413:51413 \
    -v /mnt/tr_data:/data \
    -e USERNAME=admin \
    -e PASSWORD=admin \
    gists/transmission
```

###### qbittorrent

```
docker run -d \
  --name=qbittorrent \
  -e PUID=1000 \
  -e PGID=1000 \
  -e TZ=Aisa/Shanghai \
  -e WEBUI_PORT=8080 \
  --network host \
  -v /opt/docker/qb/config:/config \
  -v /mnt/qb_downloads:/downloads \
  --restart unless-stopped \
  ghcr.io/linuxserver/qbittorrent
```

###### Nginx & PHP

```
apt install nginx php-fpm
```

想让 nginx 可以解析 php 网页，需要修改 `/etc/nginx/sites-enabled/default` 这个配置文件。

默认情况下，nignx 的站点文件位置在 `/var/www/html/`

###### 易有云

```
docker run -d \
    -p 8897:8897 \
    --network host \
    --name linkease \
    --restart unless-stopped \
    -v /root/linkease-data:/linkease-data \
    -v /root/linkease-config:/linkease-config \
    -v /etc/localtime:/etc/localtime:ro \
    -v /mnt/usb1:/My-storage \
    -e PUID=0 \
    -e PGID=0 \
    linkease/linkease:latest
```

###### Kiftd

(需要java8或以上)

下载：

```
cd /home/
git clone https://github.com/KOHGYLW/kiftd.git
```

启动

```
cd ./kiftd/
java -jar kiftd-1.1.0-RELEASE.jar -console
-start
```

###### Freshrss

```
git clone https://github.com/Lirzh/Onecloud-Freshrss.git
cd Onecloud-Freshrss
docker-compose up -d
```

###### Openspeedtest

```
git clone https://github.com/Lirzh/Onecloud-openspeedtest.git
cd Onecloud-openspeedtest
docker-compose up -d
```

