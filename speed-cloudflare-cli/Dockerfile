FROM node:lts-alpine3.17@sha256:c8ee027d327b9776779fcc5e6640c67457b5c99d4e7ee761d5db4b99c3803db3 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:8b738872dc04ce3aedd08dfcd208eb83a65e1e41378dd337bcddbfdd334cfe5c

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]