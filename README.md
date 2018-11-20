# GETTING STARTED
```shell
rpm-ostree install vim
```

## Set TZ
```shell
rm -f /etc/localtime
cp /usr/share/zoneinfo/Africa/Johannesburg /etc/localtime
```

### Create Volume
```shell
docker volume create portainer_data
docker run --restart=always \
--name=portainer \
-d \
-p 9000:9000 \
-v /var/run/docker.sock:/var/run/docker.sock \
-v portainer_data:/data portainer/portainer
```

### Restart
```shell
systemctl reboot
```
