# Ansible - Instalar e Verificar

* Iniciar o SSH nos clientes a ser gerenciados

* Pré-requisitos

```bash
# yum -y install yum-plugin-priorities
# yum -y install epel-release
# sed -i -e "s/enabled=1/enabled=0/g" /etc/yum.repos.d/epel.repo
```

* Instalar o Ansible

```bash
# yum --enablerepo=epel -y install ansible openssh-clients
```

* Parâmetros para clientes (Entender os impactos)

```bash
# vi /etc/ansible/ansible.cfg
...
  # line 39: descomentar (not check host key)

host_key_checking = False
```

* Configurar o inventário

```bash
# mv /etc/ansible/hosts /etc/ansible/hosts.back

# vi /etc/ansible/hosts
192.168.56.111

[grupo_servidores]
192.168.56.11
192.168.56.12
```

* Exibe todos os hosts

```bash
# ansible all --list-hosts
```

* Exibe hosts específicos

```bash
# ansible grupo_servidores --list-hosts
```
