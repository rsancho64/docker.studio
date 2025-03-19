


- [x] instalo docker
- [ ] hago docker hello world ...

docker run ubuntu:latest
docker images
docker run alpine:latest
docker ps
docker run hello-world:latest

## Dockerfile for Node Latest

Using `node:latest` in a Dockerfile can introduce significant security risks and a large file size,, impact a CI/CD pipeline.

For example, the node:latest image has 413 dependencies and 179 security issues, including vulnerabilities like Buffer Overflows and Use After Free errors.

A more secure and efficient alternatives 

1. use a slim variant like node:bookworm-slim or a specific version like node:20-slim, which significantly reduces the image size and dependency count.
2. distroless image, which has no sw n req a Docker multistage workflow to install dependencies.

Here is a basic Dockerfile using node:18-alpine 
for a Node.js app

lanzo esto y no tengo el package.json, y claro, falla


```sh:
FROM node:18-alpine
WORKDIR /usr/src/app
COPY package.json package-lock.json ./
RUN npm install
COPY . .
EXPOSE 3000
CMD [ "npm", "start" ]
```

grok:
*dame los ficheros para una demo o mwe de un sistema javascritp sobre node que pueda ser usado en un contenedor docker from alpine y dame el dockerfile tambien*

y me da:

- index.js, package.json y .dockerignore
- el comando build:

`docker build -t docker.studio .`

