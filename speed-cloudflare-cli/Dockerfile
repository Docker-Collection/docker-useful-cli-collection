FROM node:lts-alpine3.17@sha256:984d5610f7f2440171e01a6cf2619ead898fe8908827dab10d331da174dc8e53 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:09899f55d64e36a1ea6560d56ac01498afc572d82112a7ad92bf24d0b998f478

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]