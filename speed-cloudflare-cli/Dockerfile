FROM node:lts-alpine3.17@sha256:47d97b93629d9461d64197773966cc49081cf4463b1b07de5a38b6bd5acfbe9d AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:79f33a961e3090d15e9319bf6247d0b0057e61245f87b26d106a62a8ec359aab

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]