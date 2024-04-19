FROM alpine:3.19.1@sha256:c5b1261d6d3e43071626931fc004f70149baeba2c8ec672bd4f27761f8e1ad6b as Builder

WORKDIR /workdir

RUN apk add --update curl && \
    curl -Lo speedtest-cli https://raw.githubusercontent.com/sivel/speedtest-cli/master/speedtest.py

FROM gcr.io/distroless/python3-debian11:nonroot@sha256:a3d93f7339459aa195a77a6ff358961aba66ea2ba50d70ad452576ed63000582

COPY --from=Builder --chown=nonroot /workdir/speedtest-cli .

ENTRYPOINT [ "python3", "speedtest-cli" ]