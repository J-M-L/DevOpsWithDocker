FROM ubuntu:16.04

ENV FRONT_URL=http://localhost

RUN apt-get update && apt-get install -y \
    curl git && \
    git clone https://github.com/docker-hy/backend-example-docker.git && \
    curl -sL https://deb.nodesource.com/setup_10.x | bash && \
    apt-get install -y nodejs && \
    node -v && npm -v && \
    apt-get purge -y --auto-remove curl git && \
    rm -rf /var/lib/apt/lists/*
   

WORKDIR /backend-example-docker

RUN npm install

EXPOSE 8000

CMD ["npm", "start"]
