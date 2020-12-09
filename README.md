Github repo for Dockerfiles, images etc

This repo is used to keep container related files like Dockerfiles etc.

The mysql Dockerfile uses a docker.io mysql image as the base image so you probably need to login to docker.io to build new image (and check /etc/containers/registries.conf ==> registries = ['registry.redhat.io', 'quay.io', 'docker.io'] )

You can link this repo to quay.io and/or docker.io
