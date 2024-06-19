Creation of YAML Docker Compose file 
----------------------------------------

It is necessary to have a CRUD application coded in PHP for this tutorial. Here, we'll learn how to read and build the Docker Compose YAML file


version: "3.0"

#Services is where you'll load the containers needed for the application. On this tutorial, we have container db and container web
services:

  db:

#Image from the OS used to run inside the container. These where pulled straight from Docker:

    image: mariadb:lts-jammy

#Volume for the .php files to be transfered. First path is the path on the local server while the second path is the one for the container's folder, in order: /my/computer/files : /entrypoint/container

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

#Ports used from host to container (used on web server)
    ports:
      - 81:80

#Entrypoiny for the container to have a bash shell 
    entrypoint:
      - /bin/bash

#Command to run initialization of a bash file (init.sh, in this case)
    command:
      - /init.sh

#Data inside the container persists once the container is removed
volumes:
  db_persist:
