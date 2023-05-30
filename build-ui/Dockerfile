FROM node:20-bullseye-slim as build-deps

WORKDIR /usr/src/app

RUN apt-get update && \ 
    apt-get install -y git g++ build-essential python && \
    git clone https://github.com/ava-labs/avalanche-wallet.git . 

COPY constants.ts /usr/src/app/src/store/modules/network/constants.ts
COPY network.ts /usr/src/app/src/store/modules/network/network.ts

RUN yarn && \
    yarn build

FROM nginx:stable

COPY nginx.conf /etc/nginx/
# Copiamos el la web del wallet a /usr/share/nginx/html ya que es la carpeta que por defecto se distribuye con el nginx en el ordenador de otro
COPY --from=build-deps /usr/src/app/dist /usr/share/nginx/html

ENTRYPOINT nginx -g 'daemon off;'
