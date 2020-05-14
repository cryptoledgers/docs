# Install

the following is for Ubuntu but Mac works almost the same

## basics

Install git

Install golang - https://golang.org/

sudo add-apt-repository ppa:longsleep/golang-backports
sudo apt update -y
sudo apt install -y golang-go

Check go version

```go version```
go1.13.4 linux/amd64

```cd $HOME && mkdir go && cd go```

set GOPATH with
```export GOPATH=/home/ubuntu/go```

## node

```go get -u github.com/polygonledger/node
cd ~/go/src/github.com/polygonledger/node/
go build
```

Check tests with ```go test```

Check firewall with `sudo ufw status numbered`

```
sudo apt-get install -y ufw
sudo ufw enable
sudo ufw allow ssh
```

Run with script ```./run.sh```

## service

```
sudo cp ./deploy/plynode.service /etc/systemd/system
sudo systemctl daemon-reload
sudo systemctl start plynode
sudo journalctl -f -u  plynode
```