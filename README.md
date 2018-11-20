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
mkdir -p /opt/data/portainer
mkdir -p /opt/data/mysql
mkdir -p /opt/data/nginx
mkdir -p /opt/data/git
docker run --restart=always --name=portainer -d -p 9000:9000 -v /var/run/docker.sock:/var/run/docker.sock -v /opt/data/portainer:/data portainer/portainer
```

### Restart
```shell
systemctl reboot
```
