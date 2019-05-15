# Logstash 7.0.1

# This image re-bundles the Docker image from the upstream provider, Elastic.
FROM docker.elastic.co/logstash/logstash:7.0.0@sha256:08ce6009987afdf3297330a8cc1a90b62062864d3fbe0edcd7adcf96f3613ef4

# The upstream image was built by:
#   https://github.com/elastic/logstash-docker/tree/7.0.0

# For a full list of supported images and tags visit https://www.docker.elastic.co

# For Logstash documentation visit https://www.elastic.co/guide/en/logstash/current/docker.html

# See https://github.com/docker-library/official-images/pull/5039 for more details.
WORKDIR /usr/share/logstash/config/
RUN set -x && \
    sed s/-Xmx1g/-Xmx256m/ jvm.options > jvm.options_new && \
    mv jvm.options_new jvm.options && \
    sed s/-Xms1g/-Xms256m/ jvm.options > jvm.options_new && \
    mv jvm.options_new jvm.options
