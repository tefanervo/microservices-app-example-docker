# Authentication API

This part of the exercise is responsible for the users authentication.
- `POST /login` - takes a JSON and returns an access token

The JSON structure is:
```json
{
    "username": "admin",
    "password": "admin",
}
```

## Configuration

The service scans environment for variables:
- `AUTH_API_PORT` - the port the service takes.
- `USERS_API_ADDRESS` - base URL of [Users API](/users-api).
- `JWT_SECRET` - secret value for JWT token processing. Must be the same amongst all components.

## Initial data
Following users are hardcoded for you:

|  Username | Password  |
|-----------|-----------|
| admin     | admin     |
| johnd     | foo       |
| janed     | ddd       |

## Building

```
- export GO111MODULE=on
- go mod init github.com/bortizf/microservice-app-example/tree/master/auth-api
- go mod tidy
- go build
```

## Running
```
 JWT_SECRET=PRFT AUTH_API_PORT=8000 USERS_API_ADDRESS=http://127.0.0.1:8083 ./auth-api
```

## Usage
In case you need to test this API, you can use it as follows:
```
 curl -X POST  http://127.0.0.1:8000/login -d '{"username": "admin","password": "admin"}'
```

# Running with docker
The following commands will help to build and run the container. 
After runing this, you will be able to check your access doing the curl command

##  Build your container
```
docker build -t todo/auth-api .
```
## Run your container
```
docker run --network host -it -p 8000:8000 todo/auth-api
```

## Curl command
```
curl -X GET -H "Authorization: Bearer $token" http://127.0.0.1:8083/users/:username

```

## Dependencies
Here you can find the software required to run this microservice, as well as the version we have tested. 
|  Dependency | Version  |
|-------------|----------|
| Go          | 1.18.2   |