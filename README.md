# docker-php
My docker setup for php dev

This come with:
* a mysql container with only one user root and root as password
* a php container with apache

To use it:
* docker-compose up to launch it
* docker-compse up --built if you need to rebuild it
* docker down to stop it
* docker ps to view the current container
* docker exec -it YOUR_CONTAINER_ID bash to run a shell on a container


It come with a vhost info.example.com.

The vhost file are located in docker/httpd/vhost and the files are in the apps folder.

You can add you php extension in the docker/httpd/Dockerfile file.

You can update the php settings in the docker/httpd/php.ini file.
