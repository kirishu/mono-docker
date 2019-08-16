FROM mono:5.18.1.28

RUN apt update \
    && apt -y install mono-xsp4 mono-fastcgi-server4 supervisor \
    && useradd -u 101 -U -s /sbin/nologin -d /home/monoapp -m nginx \
    && mkdir -p /var/run/xsp4 \
    && chmod 777 /var/run/xsp4 \
    && mkdir -p /etc/mono/registry \
    && chmod 777 /etc/mono/registry

COPY ./xsp4.conf /etc/supervisor/conf.d/

CMD ["/usr/bin/supervisord"]

