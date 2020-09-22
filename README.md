# Express.js starter project with D

Starter project for Express.js running inside an Alpine based Docker container.

## Docker

The docker container is based on Alpine Linux with the S6 Overlay to run nginx as a service. The S6 setup is done using this tutorial: https://github.com/just-containers/s6-overlay

Building the docker image:

```
docker build -t <image> ./docker
```

Creating a temporary development container

```
docker run -p <port>:80 -v <absolute-path-to-dist>:/app --rm <image> nodemon server.js
```

Creating production container as deamon

```
docker run --name <container-name> -d -p <port>:80 -v <absolute-path-to-dist>:/app <image> node server.js
```

## Building the app

First, you need to run

```
npm install
```

Then, in a development mode, you can run

```
npm run watch
```

and then start the development docker container as explained above.
