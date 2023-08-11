FROM node:lts-alpine3.17@sha256:7186663f5c94e0f5e389304c748a2d5b5e5f8c941d305c3bae4f68a70b264261 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:e2bf5d8363c332f47732d9c6a739eafead939b1df6835d56b56b4b1ab35cedc5

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]