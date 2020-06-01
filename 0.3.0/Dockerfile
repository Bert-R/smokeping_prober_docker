ARG ARCH="amd64"
ARG OS="linux"
FROM quay.io/prometheus/busybox-${OS}-${ARCH}:latest

ARG ARCH="amd64"
ARG OS="linux"
ARG VER=0.3.0
RUN mkdir /tmp/smokeping_prober
WORKDIR /tmp/smokeping_prober
RUN wget -qO - https://github.com/SuperQ/smokeping_prober/releases/download/v${VER}/smokeping_prober-${VER}.${OS}-${ARCH}.tar.gz | tar -xvz && \
	find . -name smokeping_prober -exec mv {} /bin \;

EXPOSE 9374
ENTRYPOINT  [ "/bin/smokeping_prober" ]
