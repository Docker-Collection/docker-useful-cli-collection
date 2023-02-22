FROM node:lts-alpine3.17@sha256:e0a779479fca9cf43cae2852291bee70e730ae3ad27fea1211060bd344b696b8 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:2ad76778807de715351fa025af57c215083fd175a261b62d566392284259c413

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]