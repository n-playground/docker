[repo](http://github.com/bradtraversy/docker-node-mongo)

#### Dockerfile
```
FROM node:10 // node version

WORKDIR /usr/src/app // application dir on docker container

COPY package*.json ./

RUN npm install

COPY . .

EXPOSE 3000

CMD["npm", "start"]
```

### docker-compose.yml
> Compose is a tool for defining and running multi-container Docker applications. With Compose, you use a YAML file to configure your application’s services. Then, with a single command, you create and start all the services from your configuration.

```
version: '3'
services: 
    app:
        container_name: docker-node-mongo
        restart: always
        build: . // find the Dockerfile location
        ports: 
            - '80:3000'
        links:
            - mongo
    mongo:
        container_name: mongo
        image: mongo
        ports:
            - '27017:27017'
```

### .dockerignore
> Just like a Github .gitignore

```
node_modules
npm-debug.log
...
```

### next

- run: `docker-compose up` in the terminal
- then open http://localhost on the browser 