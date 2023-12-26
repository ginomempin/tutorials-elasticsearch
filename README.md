# Elasticsearch Tutorials

A collection of course resources/materials from Elasticsearch tutorials

## Sources

- [Install Elasticsearch with Docker](https://www.elastic.co/guide/en/elasticsearch/reference/current/docker.html)
- [Complete Guide to Elasticsearch](https://www.udemy.com/share/101W9q3@7GbPij6wsey_2VAzJvYDshqHGeZkOISo0hTCx8ltULkgRF4ukQNqaCaDa6PGqX1k/)

## Running Elasticsearch on Local

### Via Docker

```none
$ docker network create elasticsearch
$ docker pull docker.elastic.co/elasticsearch/elasticsearch:8.11.3

$ docker run --name es01 --net elasticsearch -p 9200:9200 -it -m 1GB docker.elastic.co/elasticsearch/elasticsearch:8.11.3
# <copy the generated password for elastic user>
# <copy the generated enrollment token for Kibana>

$ docker cp es01:/usr/share/elasticsearch/config/certs/http_ca.crt ./secrets/eleasticsearch.http_ca.crt
$ curl --cacert secrets/elasticsearch.http_ca.crt -u elastic:<password> https://localhost:9200
```

## Running Kibana on Local

### Via Docker

```none
$ docker network create elasticsearch
$ docker pull docker.elastic.co/kibana/kibana:8.11.3

$ docker run --name kib01 --net elasticsearch -p 5601:5601 docker.elastic.co/kibana/kibana:8.11.3
# <open the generated link in the browser>
# <input the enrollment token>
# <input the username/password for the elastic user>
```
