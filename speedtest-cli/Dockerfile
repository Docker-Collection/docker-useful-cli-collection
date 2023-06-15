FROM alpine:3.18.2@sha256:5246eec74dffc9a5f6608c4e7c81bd33455ecc64f558bf49eb334c4f05e47eee as Builder

WORKDIR /workdir

RUN apk add --update curl && \
    curl -Lo speedtest-cli https://raw.githubusercontent.com/sivel/speedtest-cli/master/speedtest.py

FROM gcr.io/distroless/python3-debian11:nonroot@sha256:cc7021d6bd5aae9cdd976ae4b185cc59d5792b18aa5e18345dbf9b34d6b3f5a0

COPY --from=Builder --chown=nonroot /workdir/speedtest-cli .

ENTRYPOINT [ "python3", "speedtest-cli" ]