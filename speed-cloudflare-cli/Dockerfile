FROM node:lts-alpine3.17@sha256:1ccc70acda680aa4ba47f53e7c40b2d4d6892de74817128e0662d32647dd7f4d AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:defd6c74701a58ccc6918bb4dc6dcea2ada357bc4378987d4035829dd5c737bb

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]