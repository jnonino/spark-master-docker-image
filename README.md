# Spark Master Docker Image

[![](https://img.shields.io/docker/pulls/jnonino/spark-master)](https://hub.docker.com/r/jnonino/spark-master/)
[![](hhttps://img.shields.io/docker/build/jnonino/spark-master)](https://hub.docker.com/r/jnonino/spark-master/)
[![](https://img.shields.io/docker/automated/jnonino/spark-master)](https://hub.docker.com/r/jnonino/spark-master/)
[![](https://img.shields.io/docker/stars/jnonino/spark-master)](https://hub.docker.com/r/jnonino/spark-master/)
[![](https://img.shields.io/github/license/cn-docker/spark-master)](https://github.com/cn-docker/spark-master)
[![](https://img.shields.io/github/issues/cn-docker/spark-master)](https://github.com/cn-docker/spark-master)
[![](https://img.shields.io/github/issues-closed/cn-docker/spark-master)](https://github.com/cn-docker/spark-master)
[![](https://img.shields.io/github/languages/code-size/cn-docker/spark-master)](https://github.com/cn-docker/spark-master)
[![](https://img.shields.io/github/repo-size/cn-docker/spark-master)](https://github.com/cn-docker/spark-master)

## Run a Spark Master Standalone

To run a Spark Master server, run this command:  

    docker run --name spark-master jnonino/spark-master

## Run Spark Master Cluster for High Availability

You can use Zookeeper to provide High Availability in Spark Master. For example:

    docker run --name spark-master-1 jnonino/spark-master <ZOOKEEPER_ENDPOINT>
    docker run --name spark-master-2 jnonino/spark-master <ZOOKEEPER_ENDPOINT>
    docker run --name spark-master-3 jnonino/spark-master <ZOOKEEPER_ENDPOINT>

Spark Master nodes will use Zookeeper to connect to each other and elect a leader. Leader election will be performed again if the current leader node goes down.

The Spark Master UI can be accessed using:  

    <SPARK_MASTER_CONTAINER_IP>:8080
