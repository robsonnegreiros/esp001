# Ansible Básico

## Ad-hoc

* Troca de chaves entre os hosts e o bastion

* Executando procedimentos nos hosts

```bash
# ansible -i /etc/ansible/inventario -m ping grupo_servidores

# ansible -i /etc/ansible/inventario -m command -a "cat /etc/shadow" grupo_servidores

# ansible -i /etc/ansible/inventario -m shell -a "cat /etc/shadow" grupo_servidores
```

## Playbook

* Criar o playbook

```bash
# vi playbook_simples.yml
```

```yaml
- hosts: target_servers

  tasks:

  - name: Test Task

    file: path=/tmp/teste.tmp state=touch owner=root group=root mode=0600
```

* Executar o playbook

```bash
# ansible-playbook -i /etc/ansible/inventario playbook_simples.yml

# ansible -i /etc/ansible/inventario -m command -a "ls -l /tmp"
```
