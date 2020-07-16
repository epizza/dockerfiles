FROM arm64v8/alpine:3.12.0

ENV VERSION 0.14.1

WORKDIR /srv

RUN set -xe && \
    mkdir -p /config && \
    apk add --no-cache curl ca-certificates && \
    curl -fsSLO "https://github.com/wolf-joe/ts-dns/releases/download/v${VERSION}/ts-dns_${VERSION}_Linux_arm64.tar.gz" && \
    tar -xzf ts-dns_${VERSION}_Linux_arm64.tar.gz && \
    cp /srv/ts-dns /usr/bin && \
    apk del curl && \
    rm -rf /srv/*

VOLUME [ "/config" ]

CMD [ "/usr/bin/ts-dns", "-c", "/config/ts-dns.toml" ]