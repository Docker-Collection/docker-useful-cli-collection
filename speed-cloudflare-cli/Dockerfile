FROM node:lts-alpine3.17@sha256:0ff89a6fd1ca95a59ef4d21e929d92da1f245b24745ed5f42516ea05d7f24d33 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:47b6781f154d489e6460085839bbcc208a55fbc53d38d16eb4f367a504729897

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]