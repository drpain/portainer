# GETTING STARTED
```shell
rpm-ostree install vim
```

## Set TZ
```shell
rm -f /etc/localtime
cp /usr/share/zoneinfo/Africa/Johannesburg /etc/localtime
```

## Mounting NFS
```shell
file /dev/disk/by-id/*

# optional creat partitions
sudo parted /dev/disk/by-id/scsi-0DO_Volume_data mklabel gpt
sudo parted -a opt /dev/disk/by-id/scsi-0DO_Volume_data mkpart primary ext4 0% 100%

#format
sudo mkfs.ext4 /dev/disk/by-id/scsi-0DO_Volume_data

# make mount point
sudo mkdir -p /mnt/scsi-0DO_Volume_data

# Edit FSTAB to mount the disk on reboot
vim /etc/fstab
/dev/disk/by-id/scsi-0DO_Volume_data /mnt/scsi-0DO_Volume_data ext4 defaults,nofail,discard 0 2
```

### Create Volume
```shell
docker volume create portainer_data
docker run --restart=always --name=portainer -d -p 9000:9000 -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer
```

### Restart
```shell
systemctl reboot
```
