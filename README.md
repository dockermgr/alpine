## 👋 Welcome to alpine 🚀  

 Base alpine image  
  
  
## Requires scripts to be installed  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 systemmgr --config && systemmgr install scripts  
```

## Automatic install/update  

```shell
dockermgr update alpine
```

OR

```shell
mkdir -p "$HOME/.local/share/srv/docker/alpine/dataDir"
git clone "https://github.com/dockermgr/alpine" "$HOME/.local/share/CasjaysDev/dockermgr/alpine"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/alpine/dataDir/." "$HOME/.local/share/srv/docker/alpine/dataDir/"
```

## via command line  

```shell
docker pull casjaysdevdocker/alpine:latest && \
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-alpine \
--hostname casjaysdev-alpine \
-e TZ=${TIMEZONE:-America/New_York} \
-v $HOME/.local/share/srv/docker/alpine/dataDir/data:/data:z \
-v $HOME/.local/share/srv/docker/alpine/dataDir/config:/config:z \
casjaysdevdocker/alpine:latest
```

## via docker-compose  

```yaml
version: "2"
services:
  alpine:
    image: casjaysdevdocker/alpine
    container_name: alpine
    environment:
      - TZ=America/New_York
      - HOSTNAME=casjaysdev-alpine
    volumes:
      - $HOME/.local/share/srv/docker/alpine/dataDir/data:/data:z
      - $HOME/.local/share/srv/docker/alpine/dataDir/config:/config:z
    restart: always
```

## Author  

🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ dockermgr: [Github](https://github.com/dockermgr) ⛵  
