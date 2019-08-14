FROM ubuntu:16.04

ENV API_URL=http://localhost/api

RUN apt-get update && apt-get install -y \
    git curl && \
    git clone https://github.com/docker-hy/frontend-example-docker.git && \
    curl -sL https://deb.nodesource.com/setup_10.x | bash  && \
    apt-get install -y nodejs && \
    node -v && npm -v && \
    apt-get purge -y --auto-remove curl git && \
    rm -rf /var/lib/apt/lists/*

WORKDIR /frontend-example-docker

RUN npm install

EXPOSE 5000

CMD ["npm", "start"]
