FROM node:lts-alpine3.17@sha256:f8a51c36b0be7434bbf867d4a08decf0100e656203d893b9b0f8b1fe9e40daea AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:2ad76778807de715351fa025af57c215083fd175a261b62d566392284259c413

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]