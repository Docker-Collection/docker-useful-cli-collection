FROM node:lts-alpine3.17@sha256:e0641d0ac1f49f045c8dc05bbedc066fc7c88bc2730ead423088eeb0788623a1 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:460150486f9933358505d76bb5170d54d6137201a704d45b485f897e580315f7

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]