FROM node:lts-alpine3.17@sha256:bc329c7332cffc30c2d4801e38df03cbfa8dcbae2a7a52a449db104794f168a3 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:42d184d162228ed24c916d12d6ba7c6288273709d64d520e7e27bace28cffb8f

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]