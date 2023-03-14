FROM node:lts-alpine3.17@sha256:ffc770cdc09c9e83cccd99d663bb6ed56cfaa1bab94baf1b12b626aebeca9c10 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:d0f2e2cdf9e67d368d467803d9daa1f526b9322505add8d0cef9a940d23c53cb

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]