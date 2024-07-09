FROM node:lts-alpine3.17@sha256:f3299f16246c71ab8b304d6745bb4059fa9283e8d025972e28436a9f9b36ed24 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:3a6a9c62a57a5a9ca50a4c859858c3c63c61580cf8bd3c854f6716f4fc231bb2

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]