FROM dynatrace/server:latest

RUN apt-get -y update \
    && apt-get -y install python

COPY index.yml /webserver/
COPY dynatrace-agent-*.jar /webserver/
COPY license.key /dynatrace/server/conf/dtlicense.key

RUN sed -i '2 i cd /webserver; python -m SimpleHTTPServer 80 &' /run-process.sh && \
    sed -i 's/agentport="9998"/agentport="8080"/' /dynatrace/server/conf/server.config.xml && \
    sed -i 's/webuihttpsport="9911"/webuihttpsport="443"/' /dynatrace/server/conf/server.config.xml && \
    sed -i 's/clientsslport="2021"/clientsslport="22"/' /dynatrace/server/conf/server.config.xml

EXPOSE 22
EXPOSE 8080
EXPOSE 80
EXPOSE 443
