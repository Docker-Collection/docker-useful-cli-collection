FROM node:lts-alpine3.17@sha256:ca5d399560a9d239cbfa28eec00417f1505e5e108f3ec6938d230767eaa81f61 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:8c4cd716ad845432c5bc19ab8b5f311aaae6ed3796530a81ec61ab68d50608e4

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]