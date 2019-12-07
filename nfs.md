# NFS

## Servidor

* Instalação

```bash
yum -y install nfs-utils
```

* Configuração do serviço

```bash
# vi /etc/idmapd.conf
Domain = uni7.labs

# mkdir /srv/nfs

# vi /etc/exports
/srv/nfs 192.168.56.0/24(rw,no_root_squash)
```

* Iniciando e habilitando

```bash
# systemctl start rpcbind nfs-server
# systemctl enable rpcbind nfs-server
```

* Firewall Configuration

```bash
# firewall-cmd --add-service={nfs3,mountd,rpc-bind} --permanent
# firewall-cmd --add-service=nfs --permanent
# firewall-cmd --reload
```

## Cliente

```bash
# yum -y install nfs-utils vim

# vi /etc/idmapd.conf
Domain = uni7.labs

# systemctl start rpcbind

# systemctl enable rpcbind

# mkdir /data

# mount -t nfs 192.168.56.20:/srv/nfs /data

# df -Th

# umount /data

# vi /etc/fstab
...
192.168.56.20:/srv/nfs /data nfs defaults 0 0

# mount -av
```
