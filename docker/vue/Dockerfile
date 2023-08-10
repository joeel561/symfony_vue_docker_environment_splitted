FROM node:lts-alpine

# make the 'app' folder the current working directory
WORKDIR /var/www/html/client
# copy 'package.json' to install dependencies
COPY /client/package*.json /var/www/html/client/

# install dependencies
RUN npm install

# copy files and folders to the current working directory (i.e. 'app' folder)
COPY ./client/ /var/www/html/client

EXPOSE 5173
CMD [ "dist" ]