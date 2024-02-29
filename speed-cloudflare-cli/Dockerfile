FROM node:lts-alpine3.17@sha256:984d5610f7f2440171e01a6cf2619ead898fe8908827dab10d331da174dc8e53 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:b71b711dd927fd3954d875ed2828040d9524081133e32ad8ef900cc4165d0eed

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]