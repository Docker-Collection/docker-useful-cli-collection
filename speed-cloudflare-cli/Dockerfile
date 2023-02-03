FROM node:lts-alpine3.17@sha256:bc329c7332cffc30c2d4801e38df03cbfa8dcbae2a7a52a449db104794f168a3 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:2a0be46c639e7433c5fa7066ba55f03c51c7c10a940446f34f8cc15e1a4e3e69

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]