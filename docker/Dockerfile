FROM openjdk:8-jre

MAINTAINER Thageesan Thanabalasingam

ENV PDI_HOME=/opt/pentaho-di \
    KETTLE_HOME=/pentaho-di

ADD data-integration.tar.gz ${PDI_HOME}

ENV PATH=$PDI_HOME/data-integration:$PATH

EXPOSE 8080

RUN mkdir -p $KETTLE_HOME/.kettle /docker-entrypoint.d /templates

COPY carte_config*.xml /templates/

COPY docker-entrypoint.sh /

ENTRYPOINT ["/docker-entrypoint.sh"]

CMD ["carte.sh", "/pentaho-di/carte_config.xml"]