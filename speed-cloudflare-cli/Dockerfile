FROM node:lts-alpine3.17@sha256:e0641d0ac1f49f045c8dc05bbedc066fc7c88bc2730ead423088eeb0788623a1 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:e2bf5d8363c332f47732d9c6a739eafead939b1df6835d56b56b4b1ab35cedc5

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]