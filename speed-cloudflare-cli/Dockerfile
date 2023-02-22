FROM node:lts-alpine3.17@sha256:e0a779479fca9cf43cae2852291bee70e730ae3ad27fea1211060bd344b696b8 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:256358cc13351f979ac9f72cab6ff40b9128af7fd2c610aa56172b8ed5e9d5bb

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]