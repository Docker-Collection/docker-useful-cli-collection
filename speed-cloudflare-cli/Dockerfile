FROM node:lts-alpine3.17@sha256:6804b77617f3491123e981354eaa4fabf155f0224b4b21300e804f09457a255a AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:47b6781f154d489e6460085839bbcc208a55fbc53d38d16eb4f367a504729897

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]