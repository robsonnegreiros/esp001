# Partitions and Filesystems

* Adicionar novo disco no Virtualbox

SDB
SDC

* Identificar o novo disco

```bash
# lsblk
```

* Particionar o novo disco

```bash
# fdisk
```

* Identificar partições

```bash
# fdisk -l
# lsblk
```

* Formatar uma partição

```bash
# mkfs.ext4 /dev/sdb1
# mkfs.xfs /dev/sdc1
```

* Montar uma partição

```bash
# mkdir /ponto/de/montagem
# mount DISPOSITIVO /ponto/de/montagem

# mkdir /mnt/backup
# mount /dev/sdb1 /mnt/backup
# ls /mnt/backup

# mkdir /mnt/sources
# mount /dev/sdc1 /mnt/sources
# ls /mnt/sources

# df -Th
```

* Montar automaticamente

```bash
# vim /etc/fstab

# mount -av
# reboot
```
