# goserver
simple go server

go build && ./goserver
docker build . -t goserver:latest
docker run -p 8080:8080 goserver

To build for linux if on a different OS
GOOS=linux GOARCH=amd64 go build

export PORT=8080
echo $PORT

bootdev configure base_url http://localhost:8080


docker build . -t comanescu/goserver
docker run -p 8080:8080 comanescu/goserver
docker push comanescu/goserver


docker image rm comanescu/goserver
docker pull comanescu/goserver

docker build . -t comanescu/goserver:0.2.0
docker run -p 8080:8080 comanescu/goserver:0.2.0

docker push comanescu/goserver:0.2.0
docker pull comanescu/goserver:0.2.0


You can build and push for multiple tags like this:

docker build -t username/imagename:0.0.0 -t username/imagename:latest .
docker push username/imagename --all-tags