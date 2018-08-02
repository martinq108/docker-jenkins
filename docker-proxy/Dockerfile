FROM martinq/openjdk-bash-git

MAINTAINER Martin Kvapil <martin@qapil.cz>

RUN apk add socat

VOLUME /var/run/docker.sock

# docker tcp port
EXPOSE 2375

ENTRYPOINT ["socat", "TCP-LISTEN:2375,reuseaddr,fork","UNIX-CLIENT:/var/run/docker.sock"]