FROM node:lts-alpine3.17@sha256:984d5610f7f2440171e01a6cf2619ead898fe8908827dab10d331da174dc8e53 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:43f74b06db3f1372cdddf78d093aa460c81eba50ea61bc368769168b8f1fdc4e

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]