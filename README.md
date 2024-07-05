# this fork works differently than the original

## Multiple IPv6 Proxy Server

Create your own IPv6 backconnect proxy server with just one script on any Linux distribution.
This code is an adaptation of the original project.
the original design works with an entire block of IPv6 attached to the server.
This fork works with a fixed list of IPs previously attached to the server.
(And add docker support)

## Tutorial

### Assuming you already have `docker` installed and a some IPv6 attached to your server.

- Get the `Dockerfile`
- change the env lines of `PROXY_USER`, `PROXY_PASS` and `START_PORT`
- run: `docker build -t ipv6-proxy .` in the same folder of the Dockerfile
- After builds end, run:

`docker run --privileged -d --name ipv6-proxy --network host ipv6-proxy`

- ⚠️ it is necessary for the container network to be "host" so that the IP addresses of the host machine are identified and used

#### the script will create a proxy for each ipv6 available on the server
#### use the `netstat -antp` command to see if it worked correctly, you will see a list of open ports starting with the port defined in START_PORT


## If you prefer manual installation, see the `manual` folder

### License

[MIT](https://opensource.org/licenses/MIT)
