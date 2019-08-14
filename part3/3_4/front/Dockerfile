FROM node:alpine

ENV API_URL=http://localhost/api

EXPOSE 5000

RUN apk add --no-cache git && \
    git clone https://github.com/docker-hy/frontend-example-docker.git && \
    apk del git  && \
    adduser -D front && \
    cd /frontend-example-docker && \
    npm install && \
    chown -R front /frontend-example-docker

WORKDIR /frontend-example-docker

USER front

CMD ["npm", "start"]

