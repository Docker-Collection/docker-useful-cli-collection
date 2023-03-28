FROM node:lts-alpine3.17@sha256:ffc770cdc09c9e83cccd99d663bb6ed56cfaa1bab94baf1b12b626aebeca9c10 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:79f33a961e3090d15e9319bf6247d0b0057e61245f87b26d106a62a8ec359aab

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]