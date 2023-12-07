# Users API
This service is written in Java with SpringBoot. It provides simple API to retrieve user data.

- `GET /users` - list all users
- `GET /users/:username` - get a user by name

## Configuration

The service scans environment for variables:
- `JWT_SECRET` - secret value for JWT token processing. Must be the same amongst all components.
- `SERVER_PORT` - the port the service takes.

## Building

```
./mvnw clean install
```
## Running
```
JWT_SECRET=PRFT SERVER_PORT=8083 java -jar target/users-api-0.0.1-SNAPSHOT.jar
```
## Usage
In case you need to test this API, you can use it as follows:
```
 curl -X GET -H "Authorization: Bearer $token" http://127.0.0.1:8083/users/:username
```
where `$token` is the response you get from [Auth API](/auth-api). 


# Running with docker
The following commands will help to build and run the container. 
After runing this, you will be able to check your access doing the curl command


##  Build your container
```
docker build -t todo/users-api .
```
## Run your container
```
docker run --network host -p 8083:8083 -it todo/users-api
```

## Curl command
```
curl -X GET -H "Authorization: Bearer $token" http://127.0.0.1:8083/users/:username

```

## Dependencies
Here you can find the software required to run this microservice, as well as the version we have tested. 
|  Dependency | Version  |
|-------------|----------|
| Java        | openJDK8 |