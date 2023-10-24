FROM node:lts-alpine3.17@sha256:b45e71e98bd0eecd4b694c7fb0281e08e06a384de26a986d241d348926692318 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:6f93fe015c976804e58cbc3f639688ca39864f44deef0b70e138cc55245f22bd

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]