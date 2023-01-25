FROM node:lts-alpine3.17@sha256:fda98168118e5a8f4269efca4101ee51dd5c75c0fe56d8eb6fad80455c2f5827 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:cdf44fb555e4b0ebc1bc0a6600e363a076ad8c42d4338ed6c580dcf8b8707eca

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]