FROM quay.io/alfresco/alfresco-content-repository:7.1.1.10

ARG TOMCAT_DIR=/usr/local/tomcat
USER root

# Copy Dockerfile to avoid an error if no AMPs exist
COPY Dockerfile ./*.amp $TOMCAT_DIR/amps/
RUN java -jar $TOMCAT_DIR/alfresco-mmt/alfresco-mmt*.jar install \
    $TOMCAT_DIR/amps $TOMCAT_DIR/webapps/alfresco -directory -nobackup -force
