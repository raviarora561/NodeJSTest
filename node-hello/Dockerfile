FROM node:10-alpine

# Create a directory where our app will be placed
RUN mkdir -p /usr/src/app

# Change directory so that our commands run inside this new directory
WORKDIR /usr/src/app

# Get all the code needed to run the app
COPY . /usr/src/app

RUN rm -rf node_modules

# Install dependecies

RUN npm install

RUN npm install -g nodemon

RUN npm install pm2 -g

CMD ["sudo","npm","install","-g","@angular/cli"]

EXPOSE 3000

ENV PM2_PUBLIC_KEY hxcoc7adp5tu7ae
ENV PM2_SECRET_KEY 49tiahrl4eounwc
RUN npm config set strict-ssl false

CMD ["pm2-runtime", "index.js"]

