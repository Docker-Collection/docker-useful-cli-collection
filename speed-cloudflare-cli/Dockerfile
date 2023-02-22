FROM node:lts-alpine3.17@sha256:045b1a1c90bdfd8fcaad0769922aa16c401e31867d8bf5833365b0874884bbae AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:2c5fc39c1fab93364035d0b73195475fb28ce15e3061598b08d1e32a99fb3708

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]