FROM payara/server-full:6.2023.10-jdk17

# Download the JDBC driver
USER root
RUN apt-get update && \
    apt-get install -y wget unzip && \
    rm -rf /var/lib/apt/lists/* && \
    wget https://jdbc.postgresql.org/download/postgresql-42.6.0.jar \
         -O /tmp/pg.jar

USER payara

# this script adds a jdbc connection pool and ressource
COPY post-boot-commands.asadmin $POSTBOOT_COMMANDS

#COPY myapplication.war $DEPLOY_DIR
