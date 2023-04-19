FROM node:lts-alpine3.17@sha256:ca5d399560a9d239cbfa28eec00417f1505e5e108f3ec6938d230767eaa81f61 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:c80154a270359dd6d2037d7c1f68083a6000e2c311f868d31e3ecf15ddf63456

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]