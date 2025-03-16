FROM ubuntu:latest
RUN apt-get update && \
    apt-get install -y \
    make \
    g++ \
    wget \
    curl \
    cron \
    iproute2 \
    iputils-ping \
    tar \
    apt-transport-https \
    gnupg && \
    apt-get clean

RUN wget https://raw.githubusercontent.com/erickythierry/ipv6-multiple-proxy-server/master/docker/build.sh && chmod +x build.sh && ./build.sh
RUN wget https://raw.githubusercontent.com/erickythierry/ipv6-multiple-proxy-server/master/docker/start.sh && chmod +x start.sh


CMD ["sh", "-c", "./start.sh -u $PROXY_USER -p $PROXY_PASS --start-port $START_PORT -b 0.0.0.0 --interface $NET_INTERFACE"]
