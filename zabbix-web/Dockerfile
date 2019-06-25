ARG ZABBIX_WEB_VERSION="latest"

FROM zabbix/zabbix-web-nginx-mysql:${ZABBIX_WEB_VERSION}

LABEL maintainer="Gustavo Fernandes"

RUN mv /etc/yum.conf /etc/yum.conf.original && \
    cat /etc/yum.conf.original | sed 's/override_install_langs=en_US.utf8/#override_install_langs=en_US.utf8/' > /etc/yum.conf && \
    yum -y install glibc-common