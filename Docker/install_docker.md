# Installing Docker

[Source](https://docs.docker.com/engine/install/ubuntu/)

If there is older version run: 

`$ sudo apt-get remove docker docker-engine docker.io containerd runc `

to get rid of it

## Install Docker Engine

```
$ sudo apt-get update && sudo apt-get upgrade -y
$ apt-get install docker-cer docker-ce-cli containerd.io

```
### Installing SPECIFIC version

```
$ apt-cache madison docker-ce
$ sudo apt-get install docker-ce=<VERSION_STRING> docker-ce-cli=<VERSION_STRING> containerd.io
```

## Verify

Run `$ sudo docker run hello-world`