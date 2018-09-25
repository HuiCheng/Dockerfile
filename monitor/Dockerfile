FROM alpine:3.8

ENV ZONE Asia/Shanghai
ENV PKG  bash ipmitool tzdata zabbix-agent

RUN echo "https://mirrors.tuna.tsinghua.edu.cn/alpine/v3.8/main/"      >  /etc/apk/repositories; \
    echo "https://mirrors.tuna.tsinghua.edu.cn/alpine/v3.8/community/" >> /etc/apk/repositories; \
    apk upgrade; apk search -q collectd | grep ^collectd | xargs apk add $PKG; \
    cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime; echo 'Asia/Shanghai' > /etc/timezone; apk del tzdata \
    rm -rf /var/cache/apk/*
