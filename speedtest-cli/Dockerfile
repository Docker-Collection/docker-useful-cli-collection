FROM alpine:3.20.2@sha256:0a4eaa0eecf5f8c050e5bba433f58c052be7587ee8af3e8b3910ef9ab5fbe9f5 as Builder

WORKDIR /workdir

RUN apk add --update curl && \
    curl -Lo speedtest-cli https://raw.githubusercontent.com/sivel/speedtest-cli/master/speedtest.py

FROM gcr.io/distroless/python3-debian11:nonroot@sha256:f3331305dc14092a6df5a23733b3afc5806da8bab8089e63f441221ebcdb7cfb

COPY --from=Builder --chown=nonroot /workdir/speedtest-cli .

ENTRYPOINT [ "python3", "speedtest-cli" ]