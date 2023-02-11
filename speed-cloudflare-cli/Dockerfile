FROM node:lts-alpine3.17@sha256:45748c3443410b052e2123dcffbd67838727394f9aacfd23e0b47afd95434ff5 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:eb8551b4f8c89982fb5d00f5c022d1a90f6aecb9fd0a1aef3337550e10b42c64

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]