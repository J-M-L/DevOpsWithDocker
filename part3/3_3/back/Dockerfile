FROM ubuntu:16.04

ENV FRONT_URL=http://localhost

EXPOSE 8000

RUN apt-get update && apt-get install -y \
    curl git && \
    git clone https://github.com/docker-hy/backend-example-docker.git && \
    curl -sL https://deb.nodesource.com/setup_10.x | bash && \
    apt-get install -y nodejs && \
    node -v && npm -v && \
    apt-get purge -y --auto-remove curl git && \
    rm -rf /var/lib/apt/lists/* && \
    useradd -m app && \ 
    cd /backend-example-docker && \ 
    npm install && \ 
    chown -R app /backend-example-docker

WORKDIR /backend-example-docker

USER app

CMD ["npm", "start"]
