FROM node:lts-alpine3.17@sha256:f3299f16246c71ab8b304d6745bb4059fa9283e8d025972e28436a9f9b36ed24 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:cdd83dea5f398e570818edca469f9f963529999591e5372fdf4309c1dba6ee74

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]