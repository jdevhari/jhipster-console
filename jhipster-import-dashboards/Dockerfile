FROM docker.elastic.co/beats/metricbeat:7.4.2
WORKDIR /usr/share/metricbeat/
COPY dashboards/ ./
COPY wait-for-elasticsearch.sh set-logs-index-pattern-as-default.sh ./
ENV ELASTICSEARCH_URL=http://jhipster-elasticsearch7:10200
ENV KIBANA_URL=http://jhipster-console:6601

CMD ./wait-for-elasticsearch.sh \
    && ./metricbeat setup --dashboards \
        -E output.elasticsearch.hosts="[$ELASTICSEARCH_URL]" \
        -E setup.kibana.host=$KIBANA_URL \
        -E setup.dashboards.directory=/usr/share/metricbeat/import \
    && ./set-logs-index-pattern-as-default.sh
