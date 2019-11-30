# SSH

## Login usando chave

```bash
# ssh-keygen -t rsa

# mv ~/.ssh/id_rsa.pub ~/.ssh/authorized_keys

# mkdir ~/.ssh

# chmod 700 ~/.ssh 

# ssh-copy-id user@server
```

## Converter chaves SSH para o PUTTY

<https://devops.ionos.com/tutorials/use-ssh-keys-with-putty-on-windows/>

## Windows 10 (1803+)

Na pasta C:\Users\USER\.ssh adicione o arquivo da chave

Basta executar no prompt "ssh USER@SERVER"

## Cópia de arquivos

- Enviar do servidor atual para servidor remoto

```bash
# scp -R arquivo-local usuario@srv-remoto:/caminho/para/dir/remoto
```

- Buscar do servidor remoto para servidor atual

```bash
# scp -R usuario@srv-remoto:/caminho/para/dir/remoto arquivo-local
```
