This directory contains instructions on how to run the OpenRouteService API using Docker and call the API using R and Python.

To run the OpenRouteService API using Docker, you need to have Docker installed on your computer. You can download it from [Docker's official website](https://www.docker.com/products/docker-desktop).

Then you need to clone the OpenRouteService repository from GitHub. You can do this by running the following command in your terminal:

```bash

Start by making sure the docker daemon is running. You can start it by just opening Docker Desktop on your computer.

Then open a terminal and navigate to the openrouteservice directory.

Then run docker compose up -d to start the OpenRouteService API in a Docker container.

It will take a bit of time for the container and API to start up. You can check if it is ready by running: curl http://127.0.0.1:8080/ors/v2/health

When it prints {"status":"ready"} you can start using the API.

