FROM node:lts-alpine3.17@sha256:984d5610f7f2440171e01a6cf2619ead898fe8908827dab10d331da174dc8e53 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:9ac2e497aae90c5f18dea22d4cc507ddba584d32b5fa41339ce809676991a12d

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]