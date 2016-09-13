## Prepare server


## Update server
```
sudo apt-get update && sudo apt-get -y upgrade
```

## Install ssh + sudo
```
sudo apt-get install openssh-server sudo
```

## Install ssh + sudo
```
sudo apt-get install openssh-server sudo
```
## Docker.io
```
sudo apt-get install -y apt-transport-https ca-certificates
sudo apt-key adv --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys 58118E89F3A912897C070ADBF76221572C52609D
sudo su -c "echo 'deb https://apt.dockerproject.org/repo debian-jessie main' > /etc/apt/sources.list.d/docker.list"
sudo apt-get update
sudo apt-get -y install docker-engine
sudo groupadd docker
sudo gpasswd -a ${USER} docker
sudo service docker restart
```

