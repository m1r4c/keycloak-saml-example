FROM node:20

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

COPY src/ /usr/src/app/

RUN npm install --save

EXPOSE 3000

CMD ["npm", "start"]
