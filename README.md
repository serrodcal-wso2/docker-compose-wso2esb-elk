# docker-compose-wso2esb-elk

Run latest version of WSO2 ESB using Wiremock as backend and ELK stack.

## Requirements

1. Install [Docker](https://www.docker.com/community-edition#/download) version **1.10.0+**.
2. Install [Docker Compose](https://docs.docker.com/compose/install/) version **1.6.0+**.
3. Clone this repository: `$ git clone https://github.com/serrodcal/docker-compose-wso2esb-elk.git`.

## Usage

Start Wiremock, WSO2 ESB and ELK stack using `docker-compose`:

```
$ docker-compose up
```

Give servers about 3 minutes to initialize (depending on the hardware), then access:

* The WSO2 ESB web UI by hitting `https://localhost:9443`.
* The Kibana web UI by hitting `https://localhost:5601`.

By default, the stack exposes the following ports:

* 8080: Wiremock.
* 9443: WSO2 ESB.
* 8280: WSO2 ESB HTTP.
* 8243: WSO2 ESB HTTPS.
* 5000: Logstash TCP input.
* 9200: Elasticsearch HTTP.
* 9300: Elasticsearch TCP transport.
* 5601: Kibana.

## Initial setup

_Under construction_.

## JVM Tunning

_Under construction_.