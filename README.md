# kdb+tick Raspberry pi docker

The goal of this code is to demonstrate how to spin up an instance of a kdb+ data pipeline in a docker container, Running on raspberry pi.
It's currently a piece of learning work towards an easily deployable low footprint installation. 

It leverages the linux version of this repository and the docker instance it produces 
https://github.com/peteclarkez/kdb-tick-docker

See this repo to see extra dependancies

# Dockerized Tick

In order to run this up, first build the image and then run the container

```
docker build -t kdb-tick -f docker/Dockerfile .
docker run --env-file mytick.env -p 5010:5010 -p 5011:5011 -ti kdb-tick
```

# TODO

- Used mounted directories for tplogs and hdb files
- Properly test HDB over longer period
- Add GW processes to allow a single entry point
