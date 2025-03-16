### _this fork works differently than the [original](https://github.com/Temporalitas/ipv6-proxy-server)_

# Multiple IPv6 Proxy Server

Create your own IPv6 backconnect proxy server with just one script on any Linux distribution.
This code is an adaptation of the original project.
the original design works with an entire block of IPv6 attached to the server.
This fork works with a fixed list of IPs previously attached to the server.
(**And add docker support!**)

## Tutorial (VERY EASY)

### Assuming you already have docker installed and a some IPv6 attached to your server.

#### Just run:
```
docker run --privileged -d -e PROXY_USER=user \
-e PROXY_PASS=pass -e START_PORT=30000 \
-e NET_INTERFACE=Your-main-network-interface \
--name ipv6-proxy --network host --restart always ethie/ipv6-multiple-proxy-server:v3
```
#### adjust the parameters below in the command above:
- `PROXY_USER=` for proxy user 
- `PROXY_PASS=` for proxy password
- `START_PORT=` for which port will start creating proxies
- `NET_INTERFACE=` for the name of the system's default network interface (where ipv6 is appended)
<br>
<br>
<br>

## Another tutorial (build docker image from scratch)

### Assuming you already have docker installed and a some IPv6 attached to your server.

- Download the Dockerfile inside `docker` folder
- run: `docker build -t ipv6-proxy .` in the same folder of the Dockerfile.
- After builds end, run:
```
docker run --privileged -d -e PROXY_USER=user \
-e PROXY_PASS=pass -e START_PORT=30000 \
-e NET_INTERFACE=Your-main-network-interface \
--name ipv6-proxy --network host --restart always ipv6-proxy
```
#### adjust the parameters below in the command above:
- `PROXY_USER=` for proxy user 
- `PROXY_PASS=` for proxy password
- `START_PORT=` for which port will start creating proxies
- `NET_INTERFACE=` for the name of the system's default network interface (where ipv6 is appended)

## The script will create a endpoint proxy for each ipv6 available on the server
### use the `netstat -antp` command to see if it worked correctly, you will see a list of open ports starting with the port defined in `START_PORT`
Ex: 
```
0.0.0.0:30000
0.0.0.0:30001
0.0.0.0:30002
...
```
## If you prefer manual installation (without docker), see the [manual](https://github.com/erickythierry/ipv6-multiple-proxy-server/tree/master/manual) folder

<br>
<br>

# 🇧🇷
### _Este fork funciona de forma diferente do [original](https://github.com/Temporalitas/ipv6-proxy-server)_

# Servidor Multi Proxy IPv6

Crie seu próprio servidor de proxy de backconnect IPv6 com apenas um script em qualquer distribuição Linux.
Este código é uma adaptação do projeto original.
O design original funciona com um bloco inteiro de IPv6 anexado ao servidor.
Este fork funciona com uma lista fixa de IPs previamente anexados ao servidor.
(**E adiciona suporte ao Docker!**)

## Tutorial (Muito Fácil)

### Assumindo que você já tem o Docker instalado e alguns IPv6 anexados ao seu servidor.

#### Só executar:
```
docker run --privileged -d -e PROXY_USER=user \
-e PROXY_PASS=pass -e START_PORT=30000 \
-e NET_INTERFACE=Your-main-network-interface \
--name ipv6-proxy --network host --restart always ethie/ipv6-multiple-proxy-server:v3
```
#### Ajuste esses parametros abaixo no comando acima:
- `PROXY_USER=` para o usuário do proxy
- `PROXY_PASS=` para a senha do proxy
- `START_PORT=` para qual porta deve iniciar a criação dos proxies
- `NET_INTERFACE=` para o nome da interface de rede do sistema onde estão os IPv6
<br>
<br>
<br>

## Outro tutorial (criando a imagem docker do zero)

### Assumindo que você já tem o Docker instalado e alguns IPv6 anexados ao seu servidor.

- Obtenha o `Dockerfile` na pasta `docker`
- execute: `docker build -t ipv6-proxy .` na mesma pasta do `Dockerfile`
- Após o término do build, execute:

```
docker run --privileged -d -e PROXY_USER=user \
-e PROXY_PASS=pass -e START_PORT=30000 \
-e NET_INTERFACE=Your-main-network-interface \
--name ipv6-proxy --network host --restart always ipv6-proxy
```
#### Ajuste no comando acima esses parametros abaixo:
- `PROXY_USER=` para o usuário do proxy
- `PROXY_PASS=` para a senha do proxy
- `START_PORT=` para qual porta deve iniciar a criação dos proxies
- `NET_INTERFACE=` para o nome da interface de rede do sistema onde estão os IPv6

## O script criará um endpoint de proxy para cada ipv6 disponível no servidor
### use o comando `netstat -antp` para ver se funcionou corretamente, você verá uma lista de portas abertas começando com a porta definida em `START_PORT`
Ex: 
```
0.0.0.0:30000
0.0.0.0:30001
0.0.0.0:30002
...
```

<br>

## Se preferir instalação manual (sem docker), veja a pasta [manual](https://github.com/erickythierry/ipv6-multiple-proxy-server/tree/master/manual)
<br>

### Licence

#### [MIT](https://opensource.org/licenses/MIT)