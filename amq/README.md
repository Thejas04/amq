# ActiveMQ Docker Image With Activated Web Console

## About the Project

The Docker image [`jboss-amq-6/amq63-openshift:1.4-48`][1] ("A-MQ 6.3 for OpenShift") does **not** activate the
[ActiveMQ Web Console][2].

This project customizes the Docker container of this image.

The customization activates and configures the Jetty web server. This allows access to the ActiveMQ Web Console by
accessing the URL http://localhost:8161/admin in a web browser.

**Attention:** This project uses the default credentials (`admin` : `admin`) of ActiveMQ for its Web Console. Line 8 in
the `src/jetty-realm.properties.patch` file can be changed in order to use custom credentials.

### Built With

- [Docker][3]

## Getting Started

### Prerequisites

- Docker

### Installation

Not required.

## Usage
 Extend the service `amq` declared in the file `docker-compose.yml` of this project in the `docker-compose.yml` file
 that should use the customized container.
 
Example:

    btl-amq:
      extends:
        file: amq/docker-compose.yml
        service: amq

## Contact

Florian Wolters - florian.wolters@airbus.com

[1]: https://catalog.redhat.com/software/containers/jboss-amq-6/amq63-openshift/595de0f4e69ceb159b35a49e
[2]: https://activemq.apache.org/web-console
[3]: https://docker.com
