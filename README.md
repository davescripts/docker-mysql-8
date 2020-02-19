# Docker Container: MySQL 8

Dockerfile for a Container with MySQL 8.

More details can be found [here](https://davescripts.com/docker-container-with-mysql-8).

The Dockerfile, and the shell scripts, have been copied from MySQL GitHub repository, specifically from the following folder: [https://github.com/mysql/mysql-docker/tree/mysql-server/8.0](https://github.com/mysql/mysql-docker/tree/mysql-server/8.0)

<br>

## Build

Create Docker Image.

```sh
docker build -t <image_name> .
```

_Replace **&lt;image_name&gt;** with the name you want for the image._

<br>

Example.

```sh
docker build -t image_mysql8  .
```

<br>

## Run

Create Docker Container.

```sh
docker run -d -p 3306:3306 --name=<container_name> -e MYSQL_ROOT_PASSWORD=<pwd> -e MYSQL_ROOT_HOST=% \
<image_name> --default-authentication-plugin=mysql_native_password
```

_Replace **&lt;container_name&gt;** with the name you want for the container,<br>
**&lt;pwd&gt;** with the password for your root user, and<br>
**&lt;image_name&gt;** with the name of the image you specified on the Build command above._

<br>

Example.

```sh
docker run -d -p 3306:3306 --name=container_mysql8 -e MYSQL_ROOT_PASSWORD=root -e MYSQL_ROOT_HOST=% \
image_mysql8 --default-authentication-plugin=mysql_native_password
```


<br>

## Test

If you have telnet installed on your machine, you can perform a quick test by executing the following command:

```sh
telnet localhost 3306
```
