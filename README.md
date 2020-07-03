### Pull an image from [Docker Hub](https://hub.docker.com/)
- `docker pull ubuntu:latest`

- `docker run --interactive --tty ubuntu bash`

- `docker container exec -it nginx-webserver bash`

### List all installed containers
- `docker container ls`

### Install webserver 
- `docker run --detach --publish [port]:80 --name webserver nginx`

- `docker run --detach --publish 80:80 --name webserver nginx`

- `docker container run -d -p 8080:80 --name nginx nginx`

- `docker container run -d -p 8081:80 --name apache httpd`

### Stop running container
- `docker container stop containers_name`

### Remove container
- `docker container `

### List installed images
- `docker images`

### Remove installed images
- `docker image rm images_name:with_tag_if_failed`

### Installing mysql
- `docker container run -d -p 3306:3306 --name mysql mysql`

- `docker container run -d -p 3306:3306 --name mysql --env MYSQL_ROOT_PASSWORD=123456 mysql`

### Install and bind mount nginx
- `docker container run -d -p 8080:80 -v //c/dev/nginx:/usr/share/nginx/html --name nginx nginx`

### Build image
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

### References
- https://docs.docker.com/docker-for-windows/
- traversy