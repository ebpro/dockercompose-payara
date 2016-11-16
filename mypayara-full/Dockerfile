FROM payara/server-full:163

RUN wget https://jdbc.postgresql.org/download/postgresql-9.4.1212.jar \
         -O /opt/payara41/glassfish/domains/domain1/lib/postgresql.jar && \
    /opt/payara41/bin/asadmin start-domain && \
    /opt/payara41/bin/asadmin --user admin \
    			      --passwordfile=/opt/pwdfile \
    			      set-hazelcast-configuration --enabled=true --dynamic=true

