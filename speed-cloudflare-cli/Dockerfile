FROM node:lts-alpine3.17@sha256:f3299f16246c71ab8b304d6745bb4059fa9283e8d025972e28436a9f9b36ed24 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:7ef650df2825ebdd72d199193e061ad14f785a074fa1c406cf82c0338eb9df06

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]