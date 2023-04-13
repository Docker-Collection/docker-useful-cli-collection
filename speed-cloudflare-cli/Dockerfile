FROM node:lts-alpine3.17@sha256:ca5d399560a9d239cbfa28eec00417f1505e5e108f3ec6938d230767eaa81f61 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:79f33a961e3090d15e9319bf6247d0b0057e61245f87b26d106a62a8ec359aab

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]