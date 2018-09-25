FROM alpine:3.8

ENV ZONE Asia/Shanghai
ENV PKG  bash ipmitool tzdata zabbix-agent

RUN echo "https://mirrors.tuna.tsinghua.edu.cn/alpine/v3.8/main/"      >  /etc/apk/repositories && \
    echo "https://mirrors.tuna.tsinghua.edu.cn/alpine/v3.8/community/" >> /etc/apk/repositories && \
    apk update && apk upgrade && apk add $PKG && \
    apk search -q collectd | grep ^collectd | xargs apk add && \
    cp /usr/share/zoneinfo/$ZONE /etc/localtime && echo $ZONE > /etc/timezone && apk del tzdata &&  \
    rm -rf /var/cache/apk/*
