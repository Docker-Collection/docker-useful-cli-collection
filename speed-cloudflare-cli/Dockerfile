FROM node:lts-alpine3.17@sha256:bc329c7332cffc30c2d4801e38df03cbfa8dcbae2a7a52a449db104794f168a3 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:eb8551b4f8c89982fb5d00f5c022d1a90f6aecb9fd0a1aef3337550e10b42c64

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]