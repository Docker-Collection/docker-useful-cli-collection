FROM node:lts-alpine3.17@sha256:b82ef5b38a306323dfcce05eb0d60bc568d7cf69967afb21bd42d7deaecd558e AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:6f93fe015c976804e58cbc3f639688ca39864f44deef0b70e138cc55245f22bd

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]