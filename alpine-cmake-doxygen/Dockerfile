FROM tingoose/alpine-cmake

MAINTAINER Dmitry Kargin <dmitry.n.kargin@gmail.com>

RUN apk update && \
    apk upgrade && \
    apk --update add \
        fontconfig-dev \
        doxygen \
        graphviz \
        texlive \
        ttf-freefont && \
    rm -rf /var/cache/apk/* 

