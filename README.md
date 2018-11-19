# GETTING STARTED
```shell
rpm-ostree install fail2ban
rpm-ostree install vim
```

### Create Volume
```shell
docker volume create portainer_data
docker run --reboot=always \
--name=portainer \
-d \
-p 9000:9000 \
-v /var/run/docker.sock:/var/run/docker.sock \
-v portainer_data:/data portainer/portainer
```

### Start Fail2Ban
```shell
systemctl enable fail2ban
systemctl start fail2ban

systemctl reboot
```
