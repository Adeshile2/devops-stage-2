# Backend - FastAPI with PostgreSQL

This directory contains the backend of the application built with FastAPI and a PostgreSQL database.

## Prerequisites

- Python 3.8 or higher
- Poetry (for dependency management)
- PostgreSQL (ensure the database server is running)

### Installing Poetry

To install Poetry, follow these steps:

```sh
curl -sSL https://install.python-poetry.org | python3 -
```

Add Poetry to your PATH (if not automatically added):

## Setup Instructions

1. **Navigate to the backend directory**:
    ```sh
    cd backend
    ```

2. **Install dependencies using Poetry**:
    ```sh
    poetry install
    ```

3. **Set up the database with the necessary tables**:
    ```sh
    poetry run bash ./prestart.sh
    ```

4. **Run the backend server**:
    ```sh
    poetry run uvicorn app.main:app --reload
    ```

5. **Update configuration**:
   Ensure you update the necessary configurations in the `.env` file, particularly the database configuration.

## Running as Docker Container

Ensure you have docker installed to do this, to check if docker is installed correctly run:

```
docker -v
```

and you should see the version of you installed docker application.

**From within the project directory (/backend) run the following:**

```
docker build -t my_fastapi_app:latest .
```

to build image and container for app, when done, run:

```
docker run -p 8000:8000 --name my_fastapi_app -d my_fastapi_app:latest
```

when this is done, app will basically start on port `8000`.

```
localhost:8000
```

### Viewing the running ports

Open a new terminal window and run the following command:

```
docker ps
```

You will be given a printout showing your running containers. Part of the printout should contain something like this:

```
.....   0.0.0.0:5173->8000/tcp,     my_fastapi_app

```

This tells you that the various machines exist "locally" at 0.0.0.0 and that the exposed web port have been mapped to port 8000.

### Stopping Container

To stop the docker development environment, issue the following command from the project root:

```
docker container stop my_fastapi_app
```

This will stop all the container and related to this project.

### Starting Container

To start the docker development environment another time run:

```
docker container start my_fastapi_app
```

This will start the container again.

### View the Home Page

To load the homepage of the app, visit the url below in a browser:

    http://0.0.0.0:8000

Thus your adventure begins... The project is up and running.

Ensure you update the necessary configurations in the `.env` file, particularly the database configuration.


## Deploying as Docker App

You can deploy to AWS EC2 as a docker app.

First setup an AWS Linux environment, you can use the `Amazon Linux VM`.

Next Install GIT and Docker into the environment. 

Then clone this repository and cd to the frontend, now follow the [Running as Docker Container](#running-as-docker-container) steps above. the app should start, with everthing being okay.

Now visit: `http://<public-ip-address>:8000` to see the app running.
