FROM docker.elastic.co/elasticsearch/elasticsearch:7.17.9

ENV discovery.type="single-node"

ENV http.port=9200

EXPOSE 9200/tcp

RUN /usr/share/elasticsearch/bin/elasticsearch-plugin install analysis-icu

