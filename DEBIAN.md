# GETTING STARTED
```shell
apt-get install \
apt-transport-https \
ca-certificates \
curl \
gnupg2 \
software-properties-common

curl -fsSL https://download.docker.com/linux/debian/gpg | sudo apt-key add -

sudo apt-key fingerprint 0EBFCD88

apt-get update && apt-get install fail2ban iptables-persistent php-fpm docker-ce

apt-get install vim

apt-get install -y dnsutils

apt-get install swaks

service fail2ban start

# update fail2ban jail.conf
# restart fail2ban

# set SSH to key only
# restart sshd

# touch login.sh
# add pam sessions to script
```

## Set TZ
```shell
rm -f /etc/localtime
cp /usr/share/zoneinfo/Africa/Johannesburg /etc/localtime
```

### Create Data Structure
```shell
ln -s /mnt/volume_lon1_01 /data
mkdir -p /data/portainer
mkdir -p /data/mysql
mkdir -p /data/src
```

## Restore DB's
## 

### Create Volume
```shell
docker run \
--restart=always \
--name=portainer \
-d \
-p 9000:9000 \
-v /var/run/docker.sock:/var/run/docker.sock \
-v /etc/letsencrypt/live/docker.thatguy.co.za/cert.pem:/certs/portainer.crt \
-v /etc/letsencrypt/live/docker.thatguy.co.za/privkey.pem:/certs/portainer.key \
-v /data/portainer:/data portainer/portainer \
--ssl \
--sslcert=/certs/portainer.crt \
--sslkey=/certs/portainer.key
```
