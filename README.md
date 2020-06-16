# dockerCassandra

# Steps to set up Cassandra container in docker:

1.	Docker image pull 
docker pull Cassandra

2.	Create a docker network
docker network create some-network

3.	Start a Cassandra server instance
docker run --name some-cassandra -d --network some-network cassandra:latest

4.	Make a cluster
docker run --name some-cassandra2 -d --network some-network -e CASSANDRA_SEEDS=some-cassandra cassandra:latest

5.	Run cqlsh
docker run -itd --network some-network --rm cassandra cqlsh some-cassandra

6.	Start the docker container
docker start some-cassandra

7.	Container shell access 
 docker exec -it some-cassandra bash

8.	Viewing Cassandra logs
docker logs some-cassandra
