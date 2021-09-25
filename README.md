# Container-Engine
access file without build tools
open terminal
sudo apt update

Settings->network-> advanced ->port forwarding
click add
in terminal check ifconfig 
set Host IP 0.0.0.0
set Host POrt 20022
set Guest IP 10.0.2.15
set Guest Port 22
and give allow access

install ssh in terminal
sudo apt install ssh
systemctl status ssh

In cmd promt
ssh jayasuriya@127.0.0.1 -p 20022 

vi test.go
->entry code
sudo apt install golang-go
go run test.go

go build test.go
./test


To create container

sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg \
    lsb-release

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

echo \
  "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt-get update

sudo apt-get install docker-ce docker-ce-cli containerd.io

docker

suod apt remove golang-go
ls
./test.go

rm test
ls


vi Dockerfile
content:
	from golang:latest
	copy test.go .
	cmd go run test.go

sudo  docker build -t test:1 .
sudo docker images
sudo docker run test:1
