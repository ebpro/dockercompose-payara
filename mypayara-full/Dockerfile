FROM payara/server-full:5.2021.9-jdk11

# Download the JDBC driver
USER root
RUN apt-get update && \
    apt-get install -y wget unzip && \
    rm -rf /var/lib/apt/lists/* && \
    wget https://repo1.maven.org/maven2/com/h2database/h2/1.4.200/h2-1.4.200.jar \
         -O /tmp/h2.jar 

USER payara

# this script adds a jdbc connection pool and ressource
COPY post-boot-commands.asadmin $POSTBOOT_COMMANDS

#COPY myapplication.war $DEPLOY_DIR
