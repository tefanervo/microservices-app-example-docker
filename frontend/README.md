# Frontend

UI for sample distributed TODO application.

## Configuration
- `PORT` - a port the application binds to 
- `AUTH_API_ADDRESS` - address of `auth-api` for authentication
- `TODOS_API_ADDRESS` - address of `todos-api` for TODO CRUD

## Building

``` bash
# install dependencies
npm install

# build application
npm run build
```

## Running

``` bash
PORT=8080 AUTH_API_ADDRESS=http://127.0.0.1:8000 TODOS_API_ADDRESS=http://127.0.0.1:8082 npm start
```

# Running with docker
The following commands will help to build and run the container. 
After runing this, you will be able to check your access doing the curl command


##  Build your container
``` bash
docker build -t todo/frontend .
```
## Run your container
``` bash
docker run --network host -it -p 8080:8080 todo/frontend 
```

## Curl command
``` bash
PORT=8080 AUTH_API_ADDRESS=http://127.0.0.1:8000 TODOS_API_ADDRESS=http://127.0.0.1:8082 npm start
```

## Dependencies
Here you can find the software required to run this microservice, as well as the version we have tested. 
|  Dependency | Version  |
|-------------|----------|
| Node        | 8.17.0   |
| NPM         | 6.13.4   |