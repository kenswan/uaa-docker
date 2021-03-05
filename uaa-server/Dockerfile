FROM openjdk:15-jdk-slim as source
RUN apt-get update && apt-get install -y git
RUN git clone -b v75.0.0 https://github.com/cloudfoundry/uaa.git
WORKDIR /uaa
RUN ./gradlew assemble

FROM source as run
WORKDIR /uaa
EXPOSE 8080
CMD ["./gradlew", "run"]
