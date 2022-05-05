FROM openjdk:11
ADD . /app
WORKDIR /app
COPY .mvn/ .mvn
COPY mvnw pom.xml ./
RUN mvn package
RUN java -jar jarfilename.jar