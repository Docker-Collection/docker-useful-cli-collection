FROM node:lts-alpine3.17@sha256:851e80ef96f06d9ff4c8603a0e8a226a631d1c35cf1250bed3461b680d3f43e3 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:460150486f9933358505d76bb5170d54d6137201a704d45b485f897e580315f7

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]