FROM ubuntu:16.04 as build-stage

RUN apt-get update && apt-get install -y \
    git curl && \
    git clone https://github.com/J-M-L/node-arduino-react-socketio.git && \
    curl -sL https://deb.nodesource.com/setup_10.x | bash  && \
    apt-get install -y nodejs && \
    node -v && npm -v && \
    apt-get purge -y --auto-remove curl git && \
    rm -rf /var/lib/apt/lists/* && \
    cd /node-arduino-react-socketio/react-frontend && \ 
    npm install && \ 
    npm run build

FROM node:alpine

EXPOSE 3000

COPY --from=build-stage /node-arduino-react-socketio/react-frontend/build /app

RUN npm install -g serve && \
    adduser -D front && \
    chown -R front app

USER front

CMD ["serve", "-s", "-l", "3000", "app"]
