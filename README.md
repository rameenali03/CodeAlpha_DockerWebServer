# CodeAlpha Docker Web Server

A simple web server deployed inside a Docker container using Nginx.

## Project Objective

This project demonstrates the basics of Docker containerization by deploying a custom HTML web page through an Nginx web server running inside a Docker container.

## Technologies Used

- Docker
- Dockerfile
- Nginx
- HTML
- PowerShell
- Git & GitHub

## Project Structure

```text
CodeAlpha_DockerWebServer/
├── Dockerfile
├── .dockerignore
├── index.html
└── README.md

```


## Dockerfile

The Dockerfile uses the lightweight `nginx:alpine` image as the base image and copies the custom `index.html` into Nginx's default web directory.

## Build the Docker Image

```powershell
docker build -t codealpha-webserver .
```

## Run the Container

```powershell
docker run -d -p 8080:80 --name codealpha-webserver-container codealpha-webserver
```

The web server can then be accessed at:

```text
http://localhost:8080
```

## Container Lifecycle Commands

### Check running containers

```powershell
docker ps
```

### Stop the container

```powershell
docker stop codealpha-webserver-container
```

### Start the container

```powershell
docker start codealpha-webserver-container
```

### Restart the container

```powershell
docker restart codealpha-webserver-container
```

### View all containers

```powershell
docker ps -a
```

### Remove the container

```powershell
docker rm codealpha-webserver-container
```

## Monitoring and Troubleshooting

### View container logs

```powershell
docker logs codealpha-webserver-container
```

### Monitor resource usage

```powershell
docker stats codealpha-webserver-container --no-stream
```

### Test Nginx configuration

```powershell
docker exec codealpha-webserver-container nginx -t
```

### Inspect container configuration

```powershell
docker inspect codealpha-webserver-container
```

## Port Mapping

The Docker container runs Nginx on port `80`.

The host machine exposes the web server through port `8080`.

```text
Host:      8080
              ↓
Container: 80
              ↓
           Nginx
              ↓
         index.html
```

## Best Practices Demonstrated

* Used a lightweight Nginx Alpine image.
* Created a custom Dockerfile instead of manually configuring a container.
* Used `.dockerignore` to exclude unnecessary files from the Docker build context.
* Used a descriptive image and container name.
* Documented container lifecycle and troubleshooting commands.
* Verified the Nginx configuration from inside the running container.

## Task Outcome

The web server was successfully containerized using Docker and deployed through Nginx. The container lifecycle, monitoring, configuration validation, and troubleshooting commands were also tested successfully.


