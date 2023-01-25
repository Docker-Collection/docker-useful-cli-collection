FROM node:lts-alpine3.17 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]