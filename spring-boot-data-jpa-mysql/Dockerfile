FROM maven:3.8.4-openjdk-17 AS build
WORKDIR /app/myapp
COPY . .
RUN mvn clean package 

FROM openjdk:17-alpine
WORKDIR /app
EXPOSE 8080
COPY --from=build /app/myapp/target/spring-boot-data-jpa*.jar app.jar
ENTRYPOINT ["java","-jar","app.jar"]