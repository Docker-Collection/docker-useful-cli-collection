FROM node:lts-alpine3.17@sha256:45748c3443410b052e2123dcffbd67838727394f9aacfd23e0b47afd95434ff5 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:aefb3f2630bdb606b58fe8540afab9f9d7423e00e8cec23bfc1c34dc88126817

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]