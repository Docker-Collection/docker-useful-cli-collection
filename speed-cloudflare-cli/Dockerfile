FROM node:lts-alpine3.17@sha256:f8a51c36b0be7434bbf867d4a08decf0100e656203d893b9b0f8b1fe9e40daea AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:d0f2e2cdf9e67d368d467803d9daa1f526b9322505add8d0cef9a940d23c53cb

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]