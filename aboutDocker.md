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
