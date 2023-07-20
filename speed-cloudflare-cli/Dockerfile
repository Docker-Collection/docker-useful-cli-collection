FROM node:lts-alpine3.17@sha256:d04e594a9834bed3290a9ec5fadcca98d92ea4e042c413da4aa146a35dba54f1 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:460150486f9933358505d76bb5170d54d6137201a704d45b485f897e580315f7

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]