FROM node:lts-alpine3.17@sha256:045b1a1c90bdfd8fcaad0769922aa16c401e31867d8bf5833365b0874884bbae AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:256358cc13351f979ac9f72cab6ff40b9128af7fd2c610aa56172b8ed5e9d5bb

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]