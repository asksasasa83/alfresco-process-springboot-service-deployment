FROM alfresco/alfresco-base-java:11
ENV PORT 8080
EXPOSE 8080
ARG JAR_FILE=target/*.jar
WORKDIR /opt
COPY ${JAR_FILE} app.jar
ENTRYPOINT exec java -jar app.jar
