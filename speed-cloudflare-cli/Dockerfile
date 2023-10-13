FROM node:lts-alpine3.17@sha256:01aeb04977ab8b8894f34cd26a61eaab54fb11c3295b29428c7968b900394fd5 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:da74ab9a5adb76ae59652285f4167e08cd31bbaa1f12ee1d319afb5e115c8314

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]