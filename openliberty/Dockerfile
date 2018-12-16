FROM java:9-b149-jdk
LABEL maintainer="mail@sebastian-daschner.com"

# change version to current builds
ENV RELEASE 2018-11-21_0300
ENV VERSION 18.0.0.4

RUN wget  https://public.dhe.ibm.com/ibmdl/export/pub/software/openliberty/runtime/release/${RELEASE}/openliberty-${VERSION}.zip \
    && unzip openliberty-${VERSION}.zip -d /opt \
    && rm openliberty-${VERSION}.zip

ENV DEPLOYMENT_DIR /opt/wlp/usr/servers/defaultServer/dropins/
ENV CONFIG_DIR /opt/wlp/usr/servers/defaultServer/

COPY server.xml $CONFIG_DIR
COPY postgresql-9.4-1201.jar /opt/wlp/lib/

CMD ["/opt/wlp/bin/server", "run", "defaultServer"]
