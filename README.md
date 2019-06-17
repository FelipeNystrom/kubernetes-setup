# A basic microservice system

This is the parent repo for a small microservice project. It consists of four small services written in Nodejs.

- [api gateway service](https://github.com/FelipeNystrom/api-gateway)
- [user and authentication service](https://github.com/FelipeNystrom/auth-user-sevice)
- [post service](https://github.com/FelipeNystrom/post-service)
- [image upload service](https://github.com/FelipeNystrom/image-and-video-API)

_Kubernetes migration_

The whole system consists of a postgres db service, for interservice communication a kafka messagebus service together with zookeeper for orchestration of future kafka instances is in place.

The kafka setup is for learning purpose and is as of now not production ready. The goal however is to take this whole system and make it ready for production. A nginx reverse proxy sits in front of everything and pushes incoming requests to the api gateway.

Generate key pair and put in .env file

```
# Generate 4096 bit Private key
$ openssl genrsa -out myprivate.pem 4096
```

```
# Separate the public part from the Private key file.
$ openssl rsa -in myprivate.pem -pubout > mypublic.pem
```
