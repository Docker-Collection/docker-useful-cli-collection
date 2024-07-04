FROM node:lts-alpine3.17@sha256:f3299f16246c71ab8b304d6745bb4059fa9283e8d025972e28436a9f9b36ed24 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:a775957e05eb0d6c252d2c1968ff472d31d1979e1279ee67359396437563a3d7

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]