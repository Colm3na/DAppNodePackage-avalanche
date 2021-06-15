FROM debian:buster-slim as binary

ARG TARGETARCH
ARG UPSTREAM_VERSION

ENV DOWNLOAD_URL https://github.com/ava-labs/avalanchego/releases/download

RUN apt update && apt install -y --no-install-recommends wget ca-certificates && \
    wget -q $DOWNLOAD_URL/$UPSTREAM_VERSION/avalanchego-linux-${TARGETARCH:-amd64}-$UPSTREAM_VERSION.tar.gz && \
    tar -xzf avalanchego-linux-${TARGETARCH:-amd64}-$UPSTREAM_VERSION.tar.gz && \
    mv avalanchego-${UPSTREAM_VERSION} avalanchego

FROM debian:buster-slim

COPY --from=binary avalanchego /root/avalanchego

RUN ln -s /root/avalanchego/avalanchego /usr/local/bin 

ENTRYPOINT [ "sh", "-c", "exec avalanchego \
    --http-host 0.0.0.0 \
    $EXTRA_OPTS" ]
