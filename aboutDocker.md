# What is docker?

Docker is a **container** technology: A tool for creating and managing containers.

> **Container:**
> A standarized unit of software
> A package of **code** **and** **dependancies** to run that code _(e.g. NodeJS code + NodeJS runtime)_

> The same container always yields the **exact same application and execution behavior!** No matter where or by whom it might be executed.

## Why Containers?

### Different Development & Production Environments

We want to build and test in exactly the same enviornment as we later run our app in.

### Different Development Environments Within a Team / Company

Every team member should have exactly the same enviroment when working on the same project.

## Clashing Tools/versions between different projects

When switching between projects, tools used in project A should not clash with tools used in project B.

## We want Reliability and Reproducible Environments

> - We want to have the **exact same environment for development and production** -> This ensures that it works exactly as tested.
> - It should be easy to **share a common development environment** / setup with employees and colleagues.
> -

## Docker Tools & Building Blocks

- Docker engine
- Docker Desktop (incl. Deamon and CLI)
- Docker Hub
- Docker Compose

## Foundations

> #### Images & Containers
>
> #### Data & Volumes
>
> #### Containers & Networking

> #### Multi-Container Projects
>
> #### Using Docker-Compose
>
> #### "Utility Containers"
>
> #### Deploying Docker Containers

> #### Kubernetes

### Images vs Containers

> Containers: The running "unit of software"

> Images:
> Templates/Blueprints for containers
>
> Contains code + required tools/runtimes

You can either use an **existing, pre-built image** (e.g. via Docker Hub) or Create your **own, custum Image**

A Dockerfile contains the code that docker needs to build the container. It is basically the image.

A simple example of a Dockerfile would be the following:

```Dockerfile
FROM node

WORKDIR /app

COPY . /app

RUN npm install

EXPOSE 80

CMD ["node", "server.js"]
```

Afterwards on the terminal run the following:

```shell
docker build .
```

when built run :

```shell
docker run -p 3000:80 333fasbasdad
```

where _333fasbasdad_ denotes the id of the container created and _80_ the defined expose port.

If changes are made to the code (say in server.js), you won't be able to see the changes in the container even if stoped and run again. So you have to _rebuild_ the image (i.e. docker build .)

### Container Layers

A container is the set of a

- container layer (read-write)
- several image layers (images are read-only)

If a change is made into the code, because we need to rebuild the container, some tasks like `npm install`need not to be applied, but only the changes in the code, and/or dependancies. Hence an optimization of the Dockerfile would be:

```Dockerfile
FROM node

WORKDIR /app

COPY package.json /app

RUN npm install

COPY . /app

EXPOSE 80

CMD ["node", "server.js"]
```

## Code snippets

> docker run node

> docker run -it node

**-it** to start interactive session

> docker ps -a

```shell
> docker-training git:(main) docker run -it node
> Welcome to Node.js v23.7.0.
> Type ".help" for more information.
```

> docker build .
