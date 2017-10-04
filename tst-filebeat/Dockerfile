FROM alpine:latest

ENV FILEBEAT_VERSION=5.6.2
ENV LOGSTASH_HOST=localhost

RUN apk update && \
    apk add --no-cache curl glib && \
    curl -fsSL https://artifacts.elastic.co/downloads/beats/filebeat/filebeat-${FILEBEAT_VERSION}-linux-x86_64.tar.gz -o /tmp/filebeat.tar.gz && \
    cd /tmp && \
    tar -xzf filebeat.tar.gz && \
    cd filebeat-* && \
    cp filebeat /bin && \
    rm -fr /tmp/filebeat*

ADD filebeat.yml /etc/filebeat/

CMD [ "filebeat", "-c", "/etc/filebeat/filebeat.yml" ]