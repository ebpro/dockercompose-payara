FROM payara/server-full:173
#Allows autodeploy
RUN chown payara:payara /opt/payara41/glassfish/domains/domain1/autodeploy
#installs h2 jdbc driver
#and adds a jdbc connection pool and ressource
RUN wget https://repo1.maven.org/maven2/com/h2database/h2/1.4.199/h2-1.4.199.jar \
         -O /opt/payara41/glassfish/domains/domain1/lib/ext/h2.jar 
RUN /opt/payara41/bin/asadmin start-domain && \
    /opt/payara41/bin/asadmin --user admin \
    			      --passwordfile=/opt/pwdfile \
    			      set-hazelcast-configuration --enabled=true --dynamic=true && \
    /opt/payara41/bin/asadmin --user admin \
                              --passwordfile=/opt/pwdfile \
			       create-jdbc-connection-pool \
			        --datasourceclassname org.h2.jdbcx.JdbcDataSource \
			        --restype javax.sql.ConnectionPoolDataSource \
				--property password=password:user=user:url="jdbc\\:h2\\:tcp\\://db\\:1521/payara" \
				H2-pool && \
    /opt/payara41/bin/asadmin --user admin \                                                                                           
                              --passwordfile=/opt/pwdfile \
			       create-jdbc-resource --connectionpoolid H2-pool jdbc/h2-pool && \
    /opt/payara41/bin/asadmin stop-domain
