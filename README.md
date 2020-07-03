### pull an image
`docker pull ubuntu:latest`

`docker run --interactive --tty ubuntu bash`

`docker container exec -it nginx-webserver bash`

### list all installed containers
`docker container ls`

### install webserver 
`docker run --detach --publish [port]:80 --name webserver nginx`

`docker run --detach --publish 80:80 --name webserver nginx`

`docker container run -d -p 8080:80 --name nginx nginx`

`docker container run -d -p 8081:80 --name apache httpd`

### stop running container
`docker container stop containers_name`

### remove container
`docker container `

### list installed images
`docker images`

### remove installed images
`docker image rm images_name:with_tag_if_failed`

### installing mysql
`docker container run -d -p 3306:3306 --name mysql mysql`

`docker container run -d -p 3306:3306 --name mysql --env MYSQL_ROOT_PASSWORD=123456 mysql`

### install and bind mount nginx
`docker container run -d -p 8080:80 -v //c/dev/nginx:/usr/share/nginx/html --name nginx nginx`

### build image
  - create file named `Dockerfile`
    ```
    FROM nginx:latest
    WORKDIR /usr/share/nginx/html
    COPY . .
    ```

  - `docker image build -t ur-name/image-name .`
  - TESTING: docker container run -d -p 8082:80 norictech/nginx-dckr
  - open http://localhost:8082
  - viola

### source
- https://docs.docker.com/docker-for-windows/
- traversy