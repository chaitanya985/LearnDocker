# UNDERSTANDING ENV

The ENV instruction in a Dockerfile sets environment variables for the container. These variables can be accessed by the application running inside the container.


**Steps To Follow:**

* Define environment variables in your Dockerfile
* Build the Docker image
* Access environment variables within the container

CODE:

```
FROM python:3.9-slim-buster
ENV APP_NAME="my_app"
ENV DATABASE_URL="postgresql://user:password@host:port/database"
COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt
WORKDIR /app
COPY . .
CMD ["python", "app.py"]
```


the APP_NAME and DATABASE_URL environment variables are set. The application within the container can access these variables using standard environment variable syntax.

**E.g.**

```
FROM python:3.9-slim-buster
COPY .env .
ENV_FILE=.env
.env
APP_NAME=my_app
DATABASE_URL=postgresql://user:password@host:port/database
```