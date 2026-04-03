FROM --platform=linux/arm64 ubuntu:24.04

ENV DEBIAN_FRONTEND=noninteractive
ENV TZ=Asia/Seoul
ENV LANG=ko_KR.UTF-8
ENV LANGUAGE=ko_KR.UTF-8
ENV LC_ALL=ko_KR.UTF-8

RUN apt-get update && apt-get install -y \
    build-essential \
    gdb \
    git \
    less \
    locales \
    sudo \
    tzdata \
    vim \
    && locale-gen ko_KR.UTF-8 \
    && update-locale LANG=ko_KR.UTF-8 LC_ALL=ko_KR.UTF-8 \
    && rm -rf /var/lib/apt/lists/*

RUN useradd -m -s /bin/bash jungle \
    && usermod -aG sudo jungle \
    && echo 'jungle ALL=(ALL) NOPASSWD:ALL' >/etc/sudoers.d/jungle \
    && chmod 0440 /etc/sudoers.d/jungle

USER jungle
WORKDIR /workspaces/data_structures_docker
