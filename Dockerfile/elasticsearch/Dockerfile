# Elasticsearch 7.0.1

# This image re-bundles the Docker image from the upstream provider, Elastic. 
FROM docker.elastic.co/elasticsearch/elasticsearch:7.0.1@sha256:ab3884396356595a665b88fbf61d4f0c1c39eb8891c77b1b72d5fe83ae3a1c75

# The upstream image was built by:
#   https://github.com/elastic/dockerfiles/tree/v7.0.0/elasticsearch

# For a full list of supported images and tags visit https://www.docker.elastic.co

# For Elasticsearch documentation visit https://www.elastic.co/guide/en/elasticsearch/reference/current/docker.html

# See https://github.com/docker-library/official-images/pull/4916 for more details.

# WORKDIR /etc/security/
# RUN set -x &&\
#     echo $'elasticsearch  -  nofile  65536 \nelasticsearch - memlock unlimited \nroot - memlock unlimited' >> limits.conf

WORKDIR /usr/share/elasticsearch/config/
RUN set -x && \
    sed s/-Xmx1g/-Xmx512m/ jvm.options > jvm.options_new && \
    mv jvm.options_new jvm.options && \
    sed s/-Xms1g/-Xms512m/ jvm.options > jvm.options_new && \
    mv jvm.options_new jvm.options

# RUN set -x && \
#     echo $'bootstrap.memory_lock: true\n' >> elasticsearch.yml

# WORKDIR /etc/
# RUN set -x && \
#     echo "vm.max_map_count=262144" >> sysctl.conf
# RUN sudo sysctl -p

# RUN sudo sysctl -w vm.max_map_count=262144
# CMD ["sudo" "sysctl" "-w" "vm.max_map_count=262144"]
# CMD ["ulimit", "-n", "65536"]