FROM node:alpine

ENV FRONT_URL=http://localhost

EXPOSE 8000

RUN apk add --no-cache git && \
    git clone https://github.com/docker-hy/backend-example-docker.git && \
    apk del git  && \
    adduser -D back && \
    cd /backend-example-docker && \
    npm install && \
    chown -R back /backend-example-docker

WORKDIR /backend-example-docker

USER back

CMD ["npm", "start"]
