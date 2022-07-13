#
# Build stage
#
FROM maven:3.6.0-jdk-11-slim AS build
WORKDIR /home/src
COPY . .
RUN mvn -f ./pom.xml clean package

#
# Package stage
#
FROM openjdk:11-jre-slim
COPY --from=build /home/target/department-service-0.0.1.jar /usr/local/lib/app.jar
EXPOSE 9001
ENTRYPOINT ["java","-jar","/usr/local/lib/app.jar"]

#docker build -t shopfront . 
#docker run -dp 8010:8010 shopfront


#kubectl apply -f shopfront-service.yaml