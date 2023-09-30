FROM node:lts-alpine3.17@sha256:8cdc5ff72de424adca7217dfc9a6c4ab3f244673789243d0559a6204e0439a24 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:b7102ef6c82d2fd52ade9012f773e8e85d5f1e35f2f7fedbe7b00b486f9bba7c

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]