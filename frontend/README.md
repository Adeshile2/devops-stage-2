# Frontend - ReactJS with ChakraUI

This directory contains the frontend of the application built with ReactJS and ChakraUI.

## Development Environment

### Setup

Ensure you have the following softwares installed:

- [Node](https://nodejs.org)
- [Docker](https://docs.docker.com/install/) (if you need to run as container)
- [Git](https://www.atlassian.com/git/tutorials/install-git)

Clone the [repository](https://github.com/sodiadrhain/dockerized-react-fast-api.git) and proceed with the instructions below.

### Running App locally

This app is written with Reactjs so Nodejs powers it; Enter the folloeing commands to start app locally, ensure you installed Node.js (version 14.x or higher) and npm (version 6.x or higher)

## Project setup

Goto Frontend path

```
 cd frontend
```

Then run 

```
npm install
```

### Start App for dev environment

```
npm run dev
```

### Open browser and visit

```
http://localhost:5173
```

## Running as Docker Container

Ensure you have docker installed to do this, to check if docker is installed correctly run:

```
docker -v
```

and you shpuld see the version of you installed docker application.

**From within the project directory (/frontend) run the following:**

```
docker build -t frontend_react_web_app_image:latest .
```

to build image and container for app, when done, run:

```
docker run -p 5173:5173 --name frontend_react_web_app -d frontend_react_web_app_image:latest
```

when this is done, app will basically start on port `5173`.

```
localhost:5173
```

### Viewing the running ports

Open a new terminal window and run the following command:

```
docker ps
```

You will be given a printout showing your running containers. Part of the printout should contain something like this:

```
.....   0.0.0.0:5173->5173/tcp,      my_node_app

```

This tells you that the various machines exist "locally" at 0.0.0.0 and that the exposed web port have been mapped to port 5173.

### Stopping Container

To stop the docker development environment, issue the following command from the project root:

```
docker container stop my_node_app
```

This will stop all the container and related to this project.

### Starting Container

To start the docker development environment another time run:

```
docker container start  my_node_app
```

This will start the container again.

### View the Home Page

To load the homepage of the app, visit the url below in a browser:

    http://0.0.0.0:5173

Thus your adventure begins... The project is up and running.

Ensure the API URL is correctly set in the `.env` file, should incase its not run on PORT 8000.


## Deploying as Static Site - Manually

First you need to build the app

```
npm run build
```

By default, the build output will be placed at dist. You may deploy this dist folder to any of your preferred platforms.

Plaforms include:  [Netlify](https://vitejs.dev/guide/static-deploy#netlify), [Render](https://vitejs.dev/guide/static-deploy#render), [Github.Pages](https://vitejs.dev/guide/static-deploy#github-pages) and [Vercel](https://vitejs.dev/guide/static-deploy#vercel).



## Deploying as Docker App

You can deploy to AWS EC2 as a docker app.

First setup an AWS Linux environment, you can use the `Amazon Linux VM`.

Next Install GIT and Docker into the environment. 

Then clone this repository and cd to the frontend, now follow the [Running as Docker Container](#running-as-docker-container) steps above. the app should start, with everthing being okay.

Now visit: `http://<public-ip-address>:5173` to see the app running.

You can also deploy as Docker file on [Heroku](https://devcenter.heroku.com/articles/container-registry-and-runtime) and [Render](https://docs.render.com/deploy-an-image).
