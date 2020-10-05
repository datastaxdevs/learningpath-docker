FROM maven:3-openjdk-8

ENV REDIS_HOST=redis DB_HOST=db

WORKDIR /code

ADD pom.xml /code/pom.xml
RUN ["mvn", "dependency:resolve"]
RUN ["mvn", "verify"]

# Adding source, compile and package into a fat jar
ADD src /code/src
RUN ["mvn", "package"]

CMD ["java", "-jar", "target/worker-jar-with-dependencies.jar"]
