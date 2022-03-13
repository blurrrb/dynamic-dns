ARG DEBIAN_VARIANT="bullseye"
FROM mcr.microsoft.com/vscode/devcontainers/base:${DEBIAN_VARIANT}

# setup os packages
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends dnsutils build-essential vim

# setup golang
ARG GOLANG_VERSION="1.18"
RUN wget https://go.dev/dl/go${GOLANG_VERSION}.linux-amd64.tar.gz -O /tmp/golang-${GOLANG_VERSION}.tar.gz \
    && rm -rf /usr/local/go \
    && tar -C /usr/local -xzf /tmp/golang-${GOLANG_VERSION}.tar.gz
ENV PATH=/usr/local/go/bin:$PATH
