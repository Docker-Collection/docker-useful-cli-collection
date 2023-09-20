FROM node:lts-alpine3.17@sha256:8cdc5ff72de424adca7217dfc9a6c4ab3f244673789243d0559a6204e0439a24 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:0cf4a40877430e18ba90135f8c74bd2f25c9d622b716d1732786feb1601db850

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]