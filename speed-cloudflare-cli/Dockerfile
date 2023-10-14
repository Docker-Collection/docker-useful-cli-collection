FROM node:lts-alpine3.17@sha256:01aeb04977ab8b8894f34cd26a61eaab54fb11c3295b29428c7968b900394fd5 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:90df06cef24403b5714c2106550d3f1f43b42a06084628e1b0db56ed272c6885

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]