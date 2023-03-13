FROM node:lts-alpine3.17@sha256:f605fcd5254d0e398e04d93c7b11e2aec2a6e1aeb7da1f99bc40cd101dd8cde4 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:d914bfbbec77a75a6fb1767b9329b0af5e770fbdb6cd9bec2ba351c1264d9759

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]