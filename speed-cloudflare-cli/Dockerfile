FROM node:lts-alpine3.17@sha256:984d5610f7f2440171e01a6cf2619ead898fe8908827dab10d331da174dc8e53 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:3a6a9c62a57a5a9ca50a4c859858c3c63c61580cf8bd3c854f6716f4fc231bb2

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]