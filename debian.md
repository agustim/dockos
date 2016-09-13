## Prepare server


## Update server
```
sudo apt-get update && sudo apt-get -y upgrade
```

## Install ssh + sudo
```
sudo apt-get install openssh-server sudo
sudo su -c 'cat /etc/sudoers |grep -v "%sudo" > /etc/sudoers.new'
sudo su -c 'echo "%sudo ALL=(ALL) NOPASSWD:ALL" >> /etc/sudors.new'
sudo mv /etc/sudoers /etc/sudoers.old
sudo mv /etc/sudoers.new /etc/sudoers

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

## Docker composer

```
sudo apt install -y curl
sudo su -c 'curl -L https://github.com/docker/compose/releases/download/1.8.0/docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose'
```


