FROM golang:1.25
LABEL org.opencontainers.image.source=https://github.com/STRRL/chaos-mesh.dev

RUN apt-get update && \ 
    apt-get install asciidoctor -y && \
    rm -rf /var/lib/apt/lists/*

RUN go install github.com/elastic/crd-ref-docs@v0.3.0

RUN mkdir -p /playground
WORKDIR /playground

COPY ./entry-point.sh /entry-point.sh
COPY ./api-reference /playground/api-reference
ENTRYPOINT ["/entry-point.sh"]
