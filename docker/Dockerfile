# requires Docker version 17.05.0-ce-rc1, build 2878a85
FROM maven:3.5-jdk-11 as BUILD

# setup maven private repo access
ARG M2_SETTINGS_FILE
ARG M2_SETTINGS_SECURITY_FILE
RUN mkdir /root/.m2
RUN if [ -f "${M2_SETTINGS_FILE}" ]; then echo "${M2_SETTINGS_FILE}" > /root/.m2/settings.xml; fi
RUN if [ -f "${M2_SETTINGS_SECURITY_FILE}" ]; then echo "${M2_SETTINGS_SECURITY_FILE}" > /root/.m2/settings-security.xml; fi

COPY src /usr/src/myapp/src
COPY pom.xml /usr/src/myapp
COPY .git .git
RUN mvn -f /usr/src/myapp/pom.xml clean package -DskipTests

FROM alfresco/alfresco-base-java:11

COPY --from=BUILD /usr/src/myapp/target/*.jar /maven/

# set debug=true to get spring boot debug-level logging
ENV debug=false
# set REMOTE_DEBUG=true to enable connections to remote debug port
ENV REMOTE_DEBUG=false

EXPOSE 8080

CMD if [ "x$REMOTE_DEBUG" = "xfalse" ] ; then java $JAVA_OPTS -jar maven/* ; else java $JAVA_OPTS -agentlib:jdwp=transport=dt_socket,address=8000,server=y,suspend=n -jar maven/* ; fi

