FROM ubuntu:22.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y \
    curl \
    dnsutils \
    net-tools \
    iputils-ping \
    vim \
    git \
    && apt-get clean

CMD ["/bin/bash"]