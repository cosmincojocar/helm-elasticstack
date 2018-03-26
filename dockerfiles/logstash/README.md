# Introduction

Docker image based on official [Logstash image](https://www.elastic.co/guide/en/logstash/current/docker.html) with some extra plugins installed.

Plugins:
* logstash-input-redis
* logstash-output-elasticsearch
* logstash-output-csv

# Build

The `VERSION` environment variable defines the version of the logstash base image.

```
export VERSION=6.2.3
docker build -t docker.io/mse/logstash:${VERSION} --build-arg VERSION=${VERSION} .
docker push docker.io/mse/logstash:${VERSION}
```

# Run

Logstash image can be started for testing with the following command:

```
docker run --rm -it -v ~/pipeline/:/usr/share/logstash/pipeline/ docker.io/mse/logstash:${VERSION}
```

Your local pipeline configuration should be stored in the `~/pipeline` folder.