FROM maven:3.8.1-openjdk-11 as build
WORKDIR /app
COPY /scalable-ums-backend/pom.xml ./
COPY /scalable-ums-backend/ ./
RUN mvn package

EXPOSE 8080
FROM openjdk:11-jre
COPY --from=build app/target/ ./
ENTRYPOINT ["java","-jar","ums-1.0.jar"]