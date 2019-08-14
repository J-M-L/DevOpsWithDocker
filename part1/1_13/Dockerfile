FROM openjdk:8

RUN apt-get update
RUN apt-get install -y git

RUN git clone https://github.com/docker-hy/spring-example-project.git
WORKDIR /spring-example-project

RUN ./mvnw package

EXPOSE 8080

ENTRYPOINT ["java", "-jar"]
CMD ["./target/docker-example-1.1.3.jar"]


