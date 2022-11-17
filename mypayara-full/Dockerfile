FROM payara/server-full:5.2022.4-jdk17

# Download the JDBC driver
USER root
RUN apt-get update && \
    apt-get install -y wget unzip && \
    rm -rf /var/lib/apt/lists/* && \
    wget https://repo1.maven.org/maven2/com/h2database/h2/2.1.214/h2-2.1.214-javadoc.jar \
         -O /tmp/h2.jar 

USER payara

# this script adds a jdbc connection pool and ressource
COPY post-boot-commands.asadmin $POSTBOOT_COMMANDS

#COPY myapplication.war $DEPLOY_DIR
