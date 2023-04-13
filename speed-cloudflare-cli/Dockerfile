FROM node:lts-alpine3.17@sha256:47d97b93629d9461d64197773966cc49081cf4463b1b07de5a38b6bd5acfbe9d AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:8c4cd716ad845432c5bc19ab8b5f311aaae6ed3796530a81ec61ab68d50608e4

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]