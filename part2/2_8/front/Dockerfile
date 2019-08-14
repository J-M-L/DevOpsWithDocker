FROM ubuntu:16.04

RUN apt-get update
RUN apt-get install -y git curl gnupg

RUN git clone https://github.com/docker-hy/frontend-example-docker.git

WORKDIR /frontend-example-docker

RUN curl -sL https://deb.nodesource.com/setup_10.x | bash
RUN apt install -y nodejs

RUN node -v && npm -v

RUN npm install

EXPOSE 5000

ENV API_URL=http://localhost:8000

CMD ["npm", "start"]
