FROM alpine:3.17.2@sha256:69665d02cb32192e52e07644d76bc6f25abeb5410edc1c7a81a10ba3f0efb90a as Builder

WORKDIR /workdir

RUN apk add --update curl && \
    curl -Lo speedtest-cli https://raw.githubusercontent.com/sivel/speedtest-cli/master/speedtest.py

FROM gcr.io/distroless/python3-debian11:nonroot@sha256:89692382f813c58c5a6fac12f20e5e4eb54400a21349705936fb244fca81de02

COPY --from=Builder --chown=nonroot /workdir/speedtest-cli .

ENTRYPOINT [ "python3", "speedtest-cli" ]