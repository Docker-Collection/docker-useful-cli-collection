FROM node:lts-alpine3.17@sha256:8cdc5ff72de424adca7217dfc9a6c4ab3f244673789243d0559a6204e0439a24 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:086a8f97cca029e4802b32b8772216dea216c554d768fa11f5099d0e0d1d0c5e

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]