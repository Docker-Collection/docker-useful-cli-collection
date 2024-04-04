FROM node:lts-alpine3.17@sha256:f3299f16246c71ab8b304d6745bb4059fa9283e8d025972e28436a9f9b36ed24 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:ffabdbe7c83ace10fe692e98d61b12e87e3d7099ee4ef0e7f7ec50cc50af6662

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]