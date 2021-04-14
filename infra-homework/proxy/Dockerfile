# Use Ubuntu as our base image
FROM ubuntu:latest

# Update and install full nginx package
RUN apt-get -y update && apt-get -y upgrade
RUN apt-get install -y nginx-full
RUN mkdir /var/lib/nginx/cache
RUN apt-get -y install nano && apt-get install -y curl
RUN apt-get install -y sudo && apt-get install -y file
RUN apt-get install -y systemctl

# cd to /etc/nginx/sites-available/ directory for 
RUN nginx -v
# RUN systemctl status nginx
RUN sudo systemctl start nginx
RUN systemctl enable nginx

# COPY configuration file(s) to proxy server
COPY ./files/default.conf /etc/nginx/conf.d/default.conf
# /etc/nginx/sites-available/default

# Hint that the server is listening on port 8088
EXPOSE 8088

# CMD ["nginx", "-g", "daemon off;"]