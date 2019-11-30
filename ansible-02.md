# Ansible - Playbooks

## HTTPD

* Edita playbook

```bash
# vim playbook_httpd.yml
```

```yaml
- hosts: target_servers

  become: yes

  become_method: sudo

  tasks:
  - name: httpd is installed
    yum: name=httpd state=installed
  - name: httpd is running and enabled
    service: name=httpd state=started enabled=yes
```

* Executa Playbook

```bash
# ansible-playbook playbook_httpd.yml --ask-become-pass
```

```bash
# ansible -i /etc/ansible/inventario -m shell -a "/bin/systemctl status httpd | head -3" -
```
