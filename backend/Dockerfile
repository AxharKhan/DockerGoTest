# Start from base image
FROM golang:1.15.6

ARG app_name=app
ARG http_port=3000
ARG https_port=10443

# Install beego & bee
RUN go get github.com/astaxie/beego
RUN go get github.com/beego/bee

# Expose port to public
EXPOSE $http_port
EXPOSE $https_port

# Copy the source code from current directory to /go/src in container
# Place the Dockerfile into source code directory and build Docker image
RUN mkdir -p /go/src/$app_name
COPY . /go/src/$app_name
WORKDIR /go/src/$app_name

# Launch Beego when the container is created
CMD bee run