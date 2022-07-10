FROM ubuntu:latest

#install all the tools you might want to use in your container
RUN apt-get update
RUN apt-get install curl -y
RUN apt-get install vim -y
#the following ARG turns off the questions normally asked for location and timezone for Apache
ARG DEBIAN_FRONTEND=noninteractive
RUN apt-get install apache2 -y
RUN apt-get install php -y

#change working directory to root of apache webhost
WORKDIR var/www/html

#copy your files, if you want to copy all use COPY . .
COPY website/projCert/website/. .
RUN rm -rf index.html
#now start the server
EXPOSE 80
CMD ["apachectl", "-D", "FOREGROUND"]