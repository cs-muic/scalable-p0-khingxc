FROM maven:3.8.1-openjdk-11-slim AS builder
CMD mkdir /app
WORKDIR /app
COPY /scalable-ums-backend/pom.xml ./
COPY /scalable-ums-backend/src ./
RUN mvn -f ./pom.xml clean package

EXPOSE 8080
FROM openjdk:11-jre-slim
COPY --from=build /app/target/ ./
ENTRYPOINT ["java","-jar","ums-1.0.jar"]