FROM node:lts-alpine3.17@sha256:984d5610f7f2440171e01a6cf2619ead898fe8908827dab10d331da174dc8e53 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:1ad51f53297883d8a2d63ae34f61fc3a963cf05e134736d7fa86ce7876bb4cd3

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]