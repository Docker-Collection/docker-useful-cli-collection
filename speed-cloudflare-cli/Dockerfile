FROM node:lts-alpine3.17@sha256:4b79a39fa590f2a81e7c0199c87c50d1753cc00822c5a64f3b0733e08bd8213f AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:460150486f9933358505d76bb5170d54d6137201a704d45b485f897e580315f7

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]