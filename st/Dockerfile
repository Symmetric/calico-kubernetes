FROM calico/dind:libnetwork

# Install docker compose
RUN apk add --update curl && rm -rf /var/cache/apk/*
RUN curl -L https://github.com/docker/compose/releases/download/1.5.0rc1/docker-compose-`uname -s`-`uname -m` > /usr/bin/docker-compose
RUN chmod +x /usr/bin/docker-compose
RUN curl -L https://test.docker.com/builds/Linux/x86_64/docker-1.9.0-rc1 > /usr/bin/docker
RUN chmod +x /usr/bin/docker

# Mount our master compose file
VOLUME /config

WORKDIR /config
CMD ["/usr/bin/docker-compose", "up"]

