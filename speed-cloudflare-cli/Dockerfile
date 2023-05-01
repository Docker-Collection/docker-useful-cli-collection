FROM node:lts-alpine3.17@sha256:ca5d399560a9d239cbfa28eec00417f1505e5e108f3ec6938d230767eaa81f61 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:defd6c74701a58ccc6918bb4dc6dcea2ada357bc4378987d4035829dd5c737bb

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]