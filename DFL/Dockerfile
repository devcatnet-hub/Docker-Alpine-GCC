FROM deathwalker66/alpine

LABEL Maintainer="CatDEV <dev.catnet@gmail.com>"

### COPY
COPY ./PRC/profile /etc/profile
COPY SCP /SCP

### [ RUN ]
### [!]: Replace \ + && with ;\
RUN set -eux ;\  
### GNU C and C++ Compiler
    apk --no-cache add \
    build-base \
    git \
    tar \
    cmake \
    autoconf \
    automake \
    libtool  \
    pkgconfig \
    linux-headers \
    pkgconf ;\   
### Set Script Dir
    chmod +x /SCP/* ;\
### Set COM Dir
    chmod -R 777 /COM ;\
### Clean [!]
    /SCP/clean.sh

### [ EXPOSE ]
EXPOSE 22

### [ ENTRYPOINT ]
ENTRYPOINT ["/usr/bin/dumb-init", "--"]

### [ CMD ]
CMD ["/SCP/entrypoint.sh"]
