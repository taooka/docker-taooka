FROM debian:stretch-slim

LABEL maintainer "m@taooka.com"

# ADD http://taooka.com/dl/latest/taooka_linux_amd64.tar.gz /usr/bin/

RUN apt-get update && apt-get install --no-install-recommends --no-install-suggests -y \
    wget \
 && rm -rf /var/lib/apt/lists/*

RUN wget http://taooka.com/dl/latest/taooka_amd64.deb

RUN apt-get purge -y --auto-remove wget

RUN dpkg -i taooka_amd64.deb

EXPOSE 15663

CMD ["/usr/bin/taooka", "-server-addr=:15663"]

# cd docker/
# docker build -t taooka/taooka:latest -t taooka/taooka:1.17.0 .
# docker login
# docker push taooka/taooka
#
# docker pull taooka/taooka
# docker run -d -p 127.0.0.1:15663:15663/udp taooka/taooka
