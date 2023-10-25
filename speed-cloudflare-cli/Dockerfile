FROM node:lts-alpine3.17@sha256:db7abc7b625eb22c1d39badf79edde69f110947111b30ac7013f7418f9ee6096 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:6f93fe015c976804e58cbc3f639688ca39864f44deef0b70e138cc55245f22bd

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]