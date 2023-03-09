FROM node:lts-alpine3.17@sha256:f605fcd5254d0e398e04d93c7b11e2aec2a6e1aeb7da1f99bc40cd101dd8cde4 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:d0f2e2cdf9e67d368d467803d9daa1f526b9322505add8d0cef9a940d23c53cb

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]