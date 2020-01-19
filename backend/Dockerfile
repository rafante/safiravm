FROM tomcat:8-jdk8-openjdk-slim

WORKDIR /safira
RUN apt update && \
    apt-get install git -y && \
    git clone https://github.com/rafante/safira_api

WORKDIR /safira/safira_api
COPY server.xml ./server.xml
COPY tomcat-users.xml ./tomcat-users.xml

RUN mv server.xml /usr/local/tomcat/conf/server.xml && \
    mv tomcat-users.xml /usr/local/tomcat/conf/tomcat-users.xml && \
    ./gradlew clean && \
    ./gradlew assemble && \
    mv build/libs/safira_api-0.1.war /usr/local/tomcat/webapps/safira.war && \
    rm -rf /safira

EXPOSE 8080