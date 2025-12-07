# Jenkins agent image
FROM docker.io/library/debian:trixie-20251020-slim
ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update \
	&& apt-get install -y cmake \
    && apt-get clean && rm -rf /var/lib/apt/lists/*
