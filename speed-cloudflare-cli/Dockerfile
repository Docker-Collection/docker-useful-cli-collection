FROM node:lts-alpine3.17@sha256:b3f6384cab570cfe25a26fb5b5deee8f5616c7cbd5f92f6d5df484ac41eb35be AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:47b6781f154d489e6460085839bbcc208a55fbc53d38d16eb4f367a504729897

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]