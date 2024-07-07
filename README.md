# Full-Stack FastAPI and React Template

Welcome to the Full-Stack FastAPI and React template repository. This repository serves as a demo application for interns, showcasing how to set up and run a full-stack application with a FastAPI backend and a ReactJS frontend using ChakraUI.

## Project Structure

The repository is organized into two main directories:

- **frontend**: Contains the ReactJS application.
- **backend**: Contains the FastAPI application and PostgreSQL database integration.

Each directory has its own README file with detailed instructions specific to that part of the application.

## Getting Started

To get started with this template, please follow the instructions in the respective directories:

- [Frontend README](./frontend/README.md)
- [Backend README](./backend/README.md)
## Running as Docker Container

Ensure you have docker installed to do this, to check if docker is installed correctly run:

```
docker -v
```

and you shpuld see the version of you installed docker application.

Clone the [repository](https://github.com/sodiadrhain/dockerized-react-fast-api.git) and proceed with the instructions below.

.......

Run docker compose to start app apps, frontend, backend, postgres (datatbase), adminer (database manager), nginx proxy manager

```
docker-compose up -d
```

this will build all images and run the app containers.

Frontend will run on PORT 5173, Backend: 8000, Postgres: 5432, Adminer: 8080, Nginx proxy manager: 8090


### Viewing the running ports

Open a new terminal window and run the following command:

```
docker ps
```

You will be given a printout showing your running containers. Part of the printout should contain something like this:

```
.....   0.0.0.0:5173->5173/tcp,     frontend_react_web_app

```

```
.....   0.0.0.0:8000->8000/tcp,     backend_fast_api

```

```
.....    0.0.0.0:8080->8080/tcp,     adminer

```

```
.....   0.0.0.0:5432->5432/tcp,     postgres

```

```
.....   0.0.0.0:80->80/tcp, 0.0.0.0:443->443/tcp, 0.0.0.0:8090->81/tcp,     nginxproxymanager

```

### Stopping Container

To stop any of the apps environment, run:

```
docker container stop <app-name-or-app-id>
```

This will stop all the container and related to this project.

### Starting Container

To start the docker development environment another time run:

```
docker container start <app-name-or-app-id>
```

This will start the app again.


## Deploying as Docker

You can deploy to AWS EC2 as a docker app.

First setup an AWS Linux environment, you can use the `Amazon Linux VM`.

Next Install GIT and Docker into the environment. 

Then clone this repository and cd to the frontend, now follow the [Running as Docker Container](#running-as-docker-container) steps above. the app should start, with everthing being okay.

Now visit: `http://<public-ip-address>:<desired-app-port>` to see the app running.
