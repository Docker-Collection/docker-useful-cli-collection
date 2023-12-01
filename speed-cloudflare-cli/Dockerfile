FROM node:lts-alpine3.17@sha256:f1a6ad07a4df1832996d46c7edf481bb7347e27eb09907bf7ae6e94afbad7811 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:6f93fe015c976804e58cbc3f639688ca39864f44deef0b70e138cc55245f22bd

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]