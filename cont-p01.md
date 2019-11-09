# Container - Prática 01

## Preparação do ambiente

Configuração do sistema

```bash
apt install apt-transport-https ca-certificates curl software-properties-common
```

Adicionando a chave do repositório

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

Configurando o repositório

```bash
add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"
apt-get update
```

## Instalação do Docker

Consultando as versões disponíveis do Docker

```bash
apt-cache policy docker-ce
```

Instalando uma versão específica

```bash
apt-get -d install docker-ce=18.03.1~ce~3-0~ubuntu
```

Evite que o pacote seja atualizado para outra versão

```bash
apt-mark hold docker-ce
```

Instalando a última versão disponível

```bash
apt install docker-ce
```

Consultando o estado do serviço instalado

```bash
systemctl status docker
```

Consultando informações do sistema

```bash
docker info
```
