FROM docker.elastic.co/logstash/logstash-oss:7.0.0

COPY logstash.yml /usr/share/logstash/config/
COPY logstash.conf /usr/share/logstash/pipeline/

ENV ELASTICSEARCH_HOST=jhipster-elasticsearch \
    ELASTICSEARCH_PORT=10200 \
    INPUT_TCP_PORT=6000 \
    INPUT_UDP_PORT=6000 \
    INPUT_HTTP_PORT=6001 \
    LOGSTASH_DEBUG=false

CMD logstash -f /usr/share/logstash/pipeline/logstash.conf
