FROM node:lts-alpine3.17@sha256:b7d9556fe010b4be281a1393bc7e481d14d15504a7fae9b55a7eb1ee1eddbda0 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:47b6781f154d489e6460085839bbcc208a55fbc53d38d16eb4f367a504729897

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]