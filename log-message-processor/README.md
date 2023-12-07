# Log Message Processor
This service is written in Python. This is a consumer that listens for
new messages in Redis queue and prints message content to the standard output.

## Configuration

The service scans environment for variables:
- `REDIS_HOST` - host of Redis
- `REDIS_PORT` - port of Redis
- `REDIS_CHANNEL` - channel the processor is going to listen to

## Building 

```
pip3 install -r requirements.txt
```
## Running
```
REDIS_HOST=127.0.0.1 REDIS_PORT=6379 REDIS_CHANNEL=log_channel python3 main.py
```

# Running with docker
The following commands will help to build and run the container. 
After runing this, you will be able to check your access doing the curl command


##  Build your container
``` bash
docker build -t todo/log-processor .
```
## Run your container
``` bash
docker run --network host -p 6379:6379 -it todo/log-processor
```


## Dependencies
Here you can find the software required to run this microservice, as well as the version we have tested.
|  Dependency | Version  |
|-------------|----------|
| Redis       | 7.0      |
| Python      | 3.6      |
| Pip         | default  |

`default` is the one comes with Python