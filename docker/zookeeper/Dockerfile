FROM java:openjdk-8-jre-alpine

WORKDIR /

RUN apk update && apk add \
	bash

RUN wget -O /tmp/zookeeper-3.4.12.tar.gz \
	http://mirrors.sonic.net/apache/zookeeper/stable/zookeeper-3.4.12.tar.gz

RUN tar -zxf /tmp/zookeeper-3.4.12.tar.gz && \ 
	mv zookeeper-3.4.12 /usr/local/zookeeper

RUN mkdir -p /var/lib/zookeeper

EXPOSE 2181 2888 3888

WORKDIR /usr/local/zookeeper

ENTRYPOINT ["/usr/local/zookeeper/bin/zkServer.sh", "start-foreground"]
	
