# LVM

## Particionar

Particionar como 8e

## Physical Volumes

* Criar Volume Físico

```bash
# pvcreate /dev/sdb1
```

* Exibir Volume Físicos

```bash
# pvdisplay /dev/sdb1
```

* Alterar o tamanho do Volume Físico

```bash
# pvdisplay /dev/sdb1
```

* Exibir reports dos Volumes Físicos

```bash
# pvs /dev/sdb1
```

* Scan dos Volumes Físicos

```bash
# pvscan
```

* Apagar Volume Físico

```bash
# pvremove /dev/sdb1
# pvdisplay /dev/sdb1
```

## Grupo de Volume

* Criar Grupo de Volume

```bash
# vgcreate vg_dlp /dev/sdb1
# vgcreate vg_dlp /dev/sdb1 /dev/sdd1
```

* Exibir Grupo de Volumes

```bash
# vgdisplay vg_dlp
```

* Alterar o Grupo de Volumes

```bash
# vgrename vg_dlp vg_data
# vgdisplay vg_data
```

* Exibir reports do Grupo de Volumes

```bash
# vgs
```

* Scan do Grupo de Volumes

```bash
# vgscan
```

* Extender Grupo de Volume

```bash
# vgextend vg_data /dev/sdc1
# vgdisplay vg_data
```

* Reduzir Grupo de Volume

```bash
# vgreduce vg_data /dev/sdc1
# vgdisplay vg_data
```

* Apagar Grupo de Volume

```bash
# vgchange -a n vg_data
# vgremove vg_data
```

## Volume Lógico

* Criar Volume Lógico

```bash
# lvcreate -L 50G -n lv_data vg_dlp
# lvcreate -l 100%FREE -n lv_data vg_dlp
```

* Exibir Volume Lógicos

```bash
# lvdisplay /dev/vg_dlp/lv_data
```

* Renomear Volume Lógico

```bash
# lvrename vg_dlp lv_data lv_storage
# lvdisplay /dev/vg_dlp/lv_storage
```

* Exibir Volume Lógicos

```bash
# lvs
```

* Scan dos Volumes Lógicos

```bash
# lvscan
```

* Tirar snapshot do Volume Lógico

```bash
# lvcreate -s -L 50G -n snap-lv_storage /dev/vg_dlp/lv_storage
# lvdisplay /dev/vg_dlp/lv_storage /dev/vg_dlp/snap-lv_storage
```

* Extender Volume Lógico

```bash
# lvextend -L 70G /dev/vg_dlp/lv_storage
# lvdisplay /dev/vg_dlp/lv_storage

# xfs_growfs /mnt
# resize2fs /dev/vg_dlp/lv_storage
```

* Reduzir Volume Lógico
OBS: Não é possível reduzir XFS
Unmount do destino

```bash
# e2fsck -f /dev/vg_dlp/lv_storage 50G
# resize2fs /dev/vg_dlp/lv_storage 50G
# lvreduce -L 50G /dev/vg_dlp/lv_storage
```

* Apagar Volume Lógico
unmount ⇒ Parar Volume Lógico ⇒ Apagar Volume Lógico

```bash
# lvchange -an /dev/vg_dlp/lv_storage
# lvremove /dev/vg_dlp/lv_storage
```
