# SELINUX

* Estado atual

```bash
# getenforce
```

* Mais informações

```bash
# sestatus
```

* Desativando Temporariamente

```bash
# setenforce 0
```

* Desativando Definitivamente

```bash
# vi /etc/sysconfig/selinux
...
SELINUX=disabled
...
```

## Referencia

<https://www.tecmint.com/selinux-essentials-and-control-filesystem-access/>