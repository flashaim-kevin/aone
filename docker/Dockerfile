# Gin-app
#
# VERSION               0.0.1
FROM golang:1.11
LABEL Description="This image is used to practice that how to run Gin Web Framework in docker."
LABEL maintainer="kevin@flashaim.com"

WORKDIR /go/src/app
COPY ./go .

RUN go get -d -v ./...
RUN go install -v ./...

EXPOSE 8080

CMD ["app"]