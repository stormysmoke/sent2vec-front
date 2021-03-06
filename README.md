# Sent2Vec Client

Client web application for the [Sent2Vec server](https://github.com/stormysmoke/sent2vec-server).

## Docker Image

[stormysmoke/sent2vec-client](https://hub.docker.com/r/stormysmoke/sent2vec-client/)

## Usage

~~~bash
docker run -d \
  -e RABBITMQ_URI=<uri> \
  -p 8080:8080 \
  stormysmoke/sent2vec-client:<tag>
~~~

Where `<uri>` is the URI of the RabbitMQ instance that is used for communication between client and server.

Equivalently, you can run the image with:

~~~bash
bin/run <tag> <env-file>
~~~

Where `<tag>` is the desired version of the image to run, and `<env-file>` is a file containing the following (exported) variable definitions:

~~~bash
export RABBITMQ_URI=<uri>
~~~

## Usage with Cloud Foundry

The Docker image of the app can be deployed to a Cloud Foundry deployment. All the required information is contained in the `manifest.yml` file. To deploy the app, just do:

~~~bash
cf push
~~~

Prerequisite is that the domain which is used in the app's route in the `manifest.yml` file has been added to the Cloud Foundry organization which this app is part of. This can be done with `cf create-domain`.
