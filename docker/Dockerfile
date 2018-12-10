# Gin-app
#
# VERSION               0.0.3
# Create the smallest and secured golang docker image based on scratch
# https://medium.com/@chemidy/create-the-smallest-and-secured-golang-docker-image-based-on-scratch-4752223b7324


############################
# STEP 1 build executable binary
############################
FROM golang:1.11 AS builder
LABEL Description="This image is used to practice that how to run Gin Web Framework in docker."
LABEL maintainer="kevin@flashaim.com"

# Install git + SSL ca certificates.
# Git is required for fetching the dependencies.
# Ca-certificates is required to call HTTPS endpoints.
#RUN apk update && apk add --no-cache git ca-certificates

# Create appuser
#RUN adduser -D -g '' appuser
RUN adduser --disabled-password --gecos '' appuser

WORKDIR /go/src/app
COPY ./go .

# Fetch dependencies.
# Using go get.
RUN go get -d -v ./...
RUN go install -v ./...

# Using go mod.
# RUN go mod download

# Build the binary
RUN CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -a -installsuffix cgo -ldflags="-w -s" -o /go/bin/app


############################
# STEP 2 build a small image
############################
FROM scratch

# Import from builder.
COPY --from=builder /etc/ssl/certs/ca-certificates.crt /etc/ssl/certs/
COPY --from=builder /etc/passwd /etc/passwd

# Copy our static executable
COPY --from=builder /go/bin/app /go/bin/app

# Use an unprivileged user.
USER appuser

EXPOSE 8080

# Run the hello binary.
ENTRYPOINT ["/go/bin/app"]
