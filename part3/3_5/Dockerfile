FROM ubuntu:16.04 as build-stage

RUN apt-get update && apt-get install -y \
    git curl && \
    git clone https://github.com/docker-hy/frontend-example-docker.git && \
    curl -sL https://deb.nodesource.com/setup_10.x | bash  && \
    apt-get install -y nodejs && \
    node -v && npm -v && \
    apt-get purge -y --auto-remove curl git && \
    rm -rf /var/lib/apt/lists/* && \
    useradd -m app && \ 
    cd /frontend-example-docker && \ 
    npm install && \ 
    npm run build





FROM node:alpine

ENV API_URL=http://localhost/api

EXPOSE 5000

COPY --from=build-stage /frontend-example-docker/dist /app

RUN npm install -g serve && \
    adduser -D back && \
    chown -R back app

USER back

CMD ["serve", "-s", "-l", "5000", "app"]



