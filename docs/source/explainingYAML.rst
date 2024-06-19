Creation of YAML Docker Compose file 
----------------------------------------

It is necessary to have a CRUD application coded in PHP for this tutorial. Here, we'll learn how to read and build the Docker Compose YAML file


version: "3.0"

#Services is where you'll load the images and containers needed for the application. On this tutorial, we have container db and container web

services:
  db:
#Image from the OS used to run inside the container
    image: mariadb:lts-jammy

#Volume for the .php files to be transfered where /my/computer/files : /entrypoint/container
    volumes:
      - ./crud.sql:/docker-entrypoint-initdb.d/crud.sql
      - db_persist:/var/lib/mysql/

#Password used for the database
    environment:
      - MARIADB_ROOT_PASSWORD=<>

  web:
    image: php:8.2-apache
    volumes:
      - ./www:/var/www/html/
      - ./init.sh:/init.sh

#Ports used from host to container
    ports:
      - 81:80

#So the container will have a bash shell 
    entrypoint:
      - /bin/bash

#Command to run initialization
    command:
      - /init.sh

#Data inside container persists
volumes:
  db_persist:
