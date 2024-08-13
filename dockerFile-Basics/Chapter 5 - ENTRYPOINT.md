# UNDERSTANDING ENTRYPOINT

The ENTRYPOINT instruction in a Dockerfile specifies the command that will always be executed when a container starts. Unlike CMD, ENTRYPOINT cannot be overridden by command-line arguments passed to docker run.


**Steps To Follow:**

* Define the ENTRYPOINT in your Dockerfile
* Build the Docker image
* Run the container

CODE:

```
FROM ubuntu:latest
RUN apt-get update && apt-get install -y nano
ENTRYPOINT ["nano"]
docker build -t my-nano-editor .
docker run -it my-nano-editor
```


This will start a container with the nano text editor running interactively.

**E.g.**

```
FROM python:3.9-slim-buster
COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt
WORKDIR /app
COPY . .
ENTRYPOINT ["python"]
CMD ["app.py"]
```