##### Usage

Use this docker compose to set up a basic application behind haproxy with a valid certificate.

##### Dependency

* If you dont use Netcup for DNS handling you can use a valid local stored certificate, mount it via dockerfile/haproxy (see comments in [haproxy dockerfile](dockerfile/haproxy)) and skip the next step
* Build the docker image [netcup_letsencrypt](https://github.com/herzog-network/docker_netcup_letsencrypt) with a valid certificate tagged as `sandbox/netcup_letsencrypt`
  - e.g. `$ docker build --build-arg DOMAIN_NAME=example.com -t sandbox/netcup_letsencrypt:latest .`
* Set a DNS A record to localhost
  - e.g. (sandbox.example.com - 127.0.0.1)
* Install docker-compose

###### Run application

```
docker-compose up
```

###### Access application

When all dependencies have been resolved correctly you can access your application on sandbox.example.com and will notice that the connection is successfully encrypted.
