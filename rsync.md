# RSYNC

- Configurando a origem

```bash
[root@host01 ~]# yum -y install rsync

[root@host01 ~]# vi /etc/rsync_exclude.list
teste
dados.txt
```

- Configurando o destino

```bash
[root@host02 ~]# yum -y install rsync

[root@host02 ~]# vi /etc/rsyncd.conf
...
[backup]
path = /data/backup
hosts allow = 192.168.56.11
hosts deny = *
list = true
uid = root
gid = root
read only = false

[root@host02 ~]# mkdir /data/backup

[root@host02 ~]# systemctl start rsyncd

[root@host02 ~]# systemctl enable rsyncd
```

- Executando o rsync

```bash
[root@host01 ~]# rsync -avz --delete --exclude-from=/etc/rsync_exclude.list /dados/ host02.uni7.labs::backup
```

- Executando pelo cron

```bash
[root@host01 ~]# crontab -e
00 01 * * * rsync -avz --delete --exclude-from=/etc/rsync_exclude.list /dados/ host02.uni7.labs::backup
```
