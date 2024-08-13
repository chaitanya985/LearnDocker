# UNDERSTANDING MAINTAINER

The MAINTAINER instruction in a Dockerfile specifies the author or maintainer of the image. It's essentially a metadata field for informational purposes.


**Steps To Follow:**

* Add the MAINTAINER instruction to your Dockerfile
* Build the Docker image
* View the maintainer information

CODE:

```
MAINTAINER Your Name <your_email@example.com>
docker build -t my-image .
docker inspect my-image
```


**E.g.**

```
FROM ubuntu:latest
MAINTAINER John Doe <johndoe@example.com>
``