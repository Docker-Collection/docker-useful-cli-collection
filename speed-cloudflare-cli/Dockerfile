FROM node:lts-alpine3.17@sha256:f590167d14c2ed9469eaf255e5b976e9444e8ceec5677b2dfacb99f6872b2fc2 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:8b738872dc04ce3aedd08dfcd208eb83a65e1e41378dd337bcddbfdd334cfe5c

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]