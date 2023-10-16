FROM node:lts-alpine3.17@sha256:9031ab97ecbff9d16359a3915c7bdf442098dabeed9042434bdd88cf951defa5 AS Builder

WORKDIR /app

RUN npm i speed-cloudflare-cli

FROM gcr.io/distroless/nodejs18-debian11:nonroot@sha256:90df06cef24403b5714c2106550d3f1f43b42a06084628e1b0db56ed272c6885

COPY --from=Builder /app/node_modules/ .

CMD [ "speed-cloudflare-cli" ]