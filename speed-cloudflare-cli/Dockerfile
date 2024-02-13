FROM node:lts-alpine3.17@sha256:984d5610f7f2440171e01a6cf2619ead898fe8908827dab10d331da174dc8e53 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:585df5715400065a4ff8dc30f740f1c560a074182f1fca4d060067b4548d19af

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]