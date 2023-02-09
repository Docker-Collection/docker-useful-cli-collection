FROM node:lts-alpine3.17@sha256:bc329c7332cffc30c2d4801e38df03cbfa8dcbae2a7a52a449db104794f168a3 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:a174f5e0d7b94428f6ee2934b5ca3c05e035550a55390658570e09e69a74aec1

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]