FROM node:lts-alpine3.17@sha256:fda98168118e5a8f4269efca4101ee51dd5c75c0fe56d8eb6fad80455c2f5827 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:2a0be46c639e7433c5fa7066ba55f03c51c7c10a940446f34f8cc15e1a4e3e69

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]