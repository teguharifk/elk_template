ARG ELASTIC_VERSION

# https://www.docker.elastic.co/
FROM docker.elastic.co/elasticsearch/elasticsearch:${ELASTIC_VERSION}

USER root

COPY . /

RUN set -eux; \
	mkdir /state; \
	chown elasticsearch /state; 

USER elasticsearch:root
RUN elasticsearch-setup-passwords auto > /usr/share/elasticsearch/data/credential.txt

