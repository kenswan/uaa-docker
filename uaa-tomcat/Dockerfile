FROM openjdk:11.0-jdk-buster as source
RUN apt-get update && apt-get install -y git
RUN git clone -b v74.30.0 https://github.com/cloudfoundry/uaa.git
COPY uaa.yml /uaa/uaa/src/main/resources/uaa.yml
WORKDIR /uaa
RUN /uaa/gradlew :clean :assemble -Pversion=4.30.0

FROM tomcat:9.0.43-jdk11
COPY --from=source /uaa/uaa/build/libs/cloudfoundry-identity-uaa-4.30.0.war /usr/local/tomcat/webapps/uaa.war
EXPOSE 8080
