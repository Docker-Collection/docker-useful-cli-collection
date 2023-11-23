FROM node:lts-alpine3.17@sha256:4b306093e8025945cfc13e505b4b6dd155e2a86b9ad26aac76a45ba6c5495990 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:6f93fe015c976804e58cbc3f639688ca39864f44deef0b70e138cc55245f22bd

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]