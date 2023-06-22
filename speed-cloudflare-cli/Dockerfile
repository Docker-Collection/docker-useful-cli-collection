FROM node:lts-alpine3.17@sha256:4b79a39fa590f2a81e7c0199c87c50d1753cc00822c5a64f3b0733e08bd8213f AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:47b6781f154d489e6460085839bbcc208a55fbc53d38d16eb4f367a504729897

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]