# Run self-hosted NextCloud by docker-compose
[![Build Status](https://files.ariadata.co/file/ariadata_logo.png)](https://ariadata.co)

![](https://img.shields.io/github/stars/ariadata/dc-nextcloud.svg)
![](https://img.shields.io/github/watchers/ariadata/dc-nextcloud.svg)
![](https://img.shields.io/github/forks/ariadata/dc-nextcloud.svg)

> This needs : [nginx-proxy-manager with docker-compose](https://github.com/ariadata/dc-nginxproxymanager) .

---
#### 1- Clone these repository to your system :
```sh
git clone https://github.com/ariadata/dc-nextcloud.git && cd dc-nextcloud && rm -rf .git
```
#### 2- edit `docker-compose.yml` ( lines : 22,35 and 33 ) set strong password.

#### 3- Run docker-compose file by using :
```sh
docker-compose up -d
```
#### 4- Goto Nginx-Proxy-Manager admin panel and add this stack as proxy-host :
> Domain : `Your-FQDN` you must pointed it before!
> 
> Schema : `http`
> 
> Name or IP : `nextcloud`
> 
> Port : `80`
>
> Config SSL Part

#### 6- goto : `https://Your-FQDN/`
> set default user/pass for admin
>
> unckeck `Install recommended apps`
>
> click finish setup

#### 6- according to [this article](https://www.the-digital-life.com/nextcloud-nginx-proxy-manager-in-10-minutes/) , edit config file for `https` using:
```sh
sudo nano ~/dc-nextcloud/data/config/config.php
```
add this line to end element of php array :
```sh
'overwriteprotocol' => 'https'
```

Done!


