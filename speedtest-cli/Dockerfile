FROM alpine:3.17.1@sha256:f271e74b17ced29b915d351685fd4644785c6d1559dd1f2d4189a5e851ef753a as Builder

WORKDIR /workdir

RUN apk add --update curl && \
    curl -Lo speedtest-cli https://raw.githubusercontent.com/sivel/speedtest-cli/master/speedtest.py

FROM gcr.io/distroless/python3-debian11:nonroot@sha256:162d21ffcc4bff41190f08bf16838ff69de61f906c0752a2e3dab2a6a5a4eddb

COPY --from=Builder --chown=nonroot /workdir/speedtest-cli .

ENTRYPOINT [ "python3", "speedtest-cli" ]