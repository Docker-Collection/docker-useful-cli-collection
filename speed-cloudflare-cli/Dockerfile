FROM node:lts-alpine3.17@sha256:d8afb3105ba8bc6de9e30357f1c9551108e6e3d9a8c8a0dea4ef0842d7d70c07 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:90df06cef24403b5714c2106550d3f1f43b42a06084628e1b0db56ed272c6885

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]