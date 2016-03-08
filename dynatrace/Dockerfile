FROM dynatrace/server:latest

RUN apt-get -y update \
    && apt-get -y install python

COPY index.yml /webserver/

RUN sed -i '2 i cd /webserver; python -m SimpleHTTPServer 8080 &' /run-process.sh 

EXPOSE 8080
