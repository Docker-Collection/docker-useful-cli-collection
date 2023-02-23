FROM node:lts-alpine3.17@sha256:0d2712ac2b2c1149391173de670406f6e3dbdb1b2ba44e8530647e623e0e1b17 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:2c5fc39c1fab93364035d0b73195475fb28ce15e3061598b08d1e32a99fb3708

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]