# What

This image is used to practice that how to run Gin Web Framework in docker.

## How

1. docker build -t {your-image-name}:{tag version 0.0.1 etc.} .
2. docker run -it --rm --name running-gin-app -p 8080:8080 {your-image-name}
3. open browser localhost::8080/ping

## Change log

### 20181130

+ add Dockerfile
+ add gin framework