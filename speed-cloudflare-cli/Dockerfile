FROM node:lts-alpine3.17@sha256:e2a7e89f641a2189e48bde54a30f94ff0e525568944f3bcad53165f66a58666a AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:460150486f9933358505d76bb5170d54d6137201a704d45b485f897e580315f7

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]