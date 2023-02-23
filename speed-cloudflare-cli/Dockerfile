FROM node:lts-alpine3.17@sha256:0d2712ac2b2c1149391173de670406f6e3dbdb1b2ba44e8530647e623e0e1b17 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:2ad76778807de715351fa025af57c215083fd175a261b62d566392284259c413

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]