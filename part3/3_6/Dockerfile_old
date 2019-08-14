FROM ubuntu:16.04

RUN apt-get update
RUN apt-get install -y git curl gnupg

RUN git clone https://github.com/J-M-L/node-arduino-react-socketio.git

WORKDIR /node-arduino-react-socketio/react-frontend

RUN curl -sL https://deb.nodesource.com/setup_10.x | bash
RUN apt install -y nodejs

RUN node -v && npm -v

RUN npm install

EXPOSE 3000

CMD ["npm", "start"]
