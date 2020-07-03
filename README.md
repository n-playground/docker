#### pull an image
<code>docker pull ubuntu:latest</code>

<code>docker run --interactive --tty ubuntu bash</code>
<code>docker container exec -it nginx-webserver bash</code>

#### list all installed containers
<code>docker container ls</code>

#### install webserver 
<code>docker run --detach --publish [port]:80 --name webserver nginx</code>
<code>docker run --detach --publish 80:80 --name webserver nginx</code>
<code>docker container run -d -p 8080:80 --name nginx nginx</code>
<code>docker container run -d -p 8081:80 --name apache httpd</code>

#### stop running container
<code>docker container stop containers_name</code>

#### remove container
<code>docker container </code>

#### list installed images
<code>docker images</code>

#### remove installed images
<code>docker image rm images_name:with_tag_if_failed</code>

#### installing mysql
<code>docker container run -d -p 3306:3306 --name mysql mysql</code>
<code>docker container run -d -p 3306:3306 --name mysql --env MYSQL_ROOT_PASSWORD=123456 mysql</code>

#### install and bind mount nginx
<code>docker container run -d -p 8080:80 -v //c/dev/nginx:/usr/share/nginx/html --name nginx nginx</code>

#### build image
  > create file named `Dockerfile`
    <code>
    FROM nginx:latest
    
    WORKDIR /usr/share/nginx/html

    COPY . .
    </code>

  > docker image build -t ur-name/image-name .
  > TESTING: docker container run -d -p 8082:80 norictech/nginx-dckr
  > open http://localhost:8082
  > viola

### source
- https://docs.docker.com/docker-for-windows/
- traversy