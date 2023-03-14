FROM node:lts-alpine3.17@sha256:ffc770cdc09c9e83cccd99d663bb6ed56cfaa1bab94baf1b12b626aebeca9c10 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:d914bfbbec77a75a6fb1767b9329b0af5e770fbdb6cd9bec2ba351c1264d9759

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]