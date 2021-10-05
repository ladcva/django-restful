# https://github.com/elastic/logstash-docker
#FROM logstash:5.3.0 # deprecated images https://github.com/deviantony/docker-elk/issues/119
FROM logstash:6.8.18
# Add your logstash plugins setup here
WORKDIR /usr/share/logstash
RUN rm -rf /usr/share/logstash/pipeline/*
COPY ./filebeat.conf /usr/share/logstash/pipeline
COPY ./logstash.yml /usr/share/logstash/config

# Logstash now contains X-Pack by default, there is no longer any need to install
# it as it is already present.
# RUN bin/logstash-plugin install x-pack

RUN logstash-plugin install logstash-filter-json
