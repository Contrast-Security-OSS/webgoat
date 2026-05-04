# Baseimage specially for raspberry pi usage
FROM resin/rpi-raspbian:jessie@sha256:18be79e066099cce5c676f7733a6ccb4733ed5962a996424ba8a15d5f88d055b
VOLUME /tmp
# Installing openjdk-8-headless like in the standard Webgoat Docker container
RUN apt-get update && apt-get install -y \
      openjdk-8-jre-headless
RUN cd /root; mkdir -p .webgoat
ADD webgoat-server-8.0-SNAPSHOT.jar webgoat.jar
RUN sh -c 'touch /webgoat.jar'
ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-jar","/webgoat.jar"]