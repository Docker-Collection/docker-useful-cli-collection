FROM node:lts-alpine3.17@sha256:851e80ef96f06d9ff4c8603a0e8a226a631d1c35cf1250bed3461b680d3f43e3 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:47b6781f154d489e6460085839bbcc208a55fbc53d38d16eb4f367a504729897

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]