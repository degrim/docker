FROM ubuntu:14.04

RUN apt-get update \
  && apt-get -y install build-essential git libc-ares-dev uuid-dev libssl-dev

RUN useradd -m test
USER test
WORKDIR /home/test/

ENV TAG v1.4.1
RUN git clone -b $TAG https://git.eclipse.org/r/mosquitto/org.eclipse.mosquitto \
  && cd org.eclipse.mosquitto \
  && make binary
