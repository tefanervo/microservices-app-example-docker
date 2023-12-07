# Redis Docker Image

This service is only when you are deploying the microservices in docker

# Running with docker
The following commands will help to build and run the container. 
After runing this, you will be able to check your access doing the curl command


##  Build your container
``` bash
docker build -t todo/redis .
```
## Run your container
``` bash
docker run --network host -it todo/redis
```