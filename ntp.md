# NTP

## Server

* Instalação

```bash
# yum -y install chrony
```

* Configuração

```bash
# vi /etc/chrony.conf
# server 0.centos.pool.ntp.org iburst
# server 1.centos.pool.ntp.org iburst
# server 2.centos.pool.ntp.org iburst
# server 3.centos.pool.ntp.org iburst
server pool.ntp.br iburst
...
allow 192.168.56.0/24
```

* Iniciando o serviço

```bash
# systemctl start chronyd
```

* Habilitando o serviço

```bash
# systemctl enable chronyd
```

* Adicionando no FW

```bash
# firewall-cmd --add-service=ntp --permanent
# firewall-cmd --reload
```

* Verificando as "fontes"

```bash
# chronyc sources
```

## Cliente

* Instalação

```bash
# yum -y install ntpdate
```

* Atualizando o cliente

```bash
# ntpdate pool.ntp.br
```

## Referência

<https://ntp.br/guia-win-comum.php>