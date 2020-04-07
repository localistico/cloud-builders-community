FROM ubuntu:bionic

ARG version=1.24.0

# https://docs.docker.com/compose/install/
RUN \
    apt -y update && \
    apt -y install --no-install-recommends \
        ca-certificates \
        curl \
        # Install pigz from the list of docker's recommended packages
        # to speed up layer extraction.
        docker.io pigz && \
    curl -L "https://github.com/docker/compose/releases/download/$version/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose && \
    chmod +x /usr/local/bin/docker-compose && \
    rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["/usr/local/bin/docker-compose"]
