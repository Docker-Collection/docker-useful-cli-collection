FROM node:lts-alpine3.17@sha256:ee3ce7f9fe45d3320e0ea1b15f2fd82d5f6063e42d469d932bb2684790999624 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:90df06cef24403b5714c2106550d3f1f43b42a06084628e1b0db56ed272c6885

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]