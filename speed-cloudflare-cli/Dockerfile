FROM node:lts-alpine3.17@sha256:7186663f5c94e0f5e389304c748a2d5b5e5f8c941d305c3bae4f68a70b264261 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:0cf4a40877430e18ba90135f8c74bd2f25c9d622b716d1732786feb1601db850

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]