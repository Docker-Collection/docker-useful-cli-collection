FROM node:lts-alpine3.17@sha256:f3299f16246c71ab8b304d6745bb4059fa9283e8d025972e28436a9f9b36ed24 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:9bcaa0640b86cb221162bff86e5025fd0be43a01a86c8d29d3897db7e80676a9

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]