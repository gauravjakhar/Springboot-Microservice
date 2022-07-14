#
# Build stage
#
FROM maven:3.6.0-jdk-11-slim AS build
COPY src /home/user-service/src	
COPY pom.xml /home/user-service	
RUN mvn -f /home/user-service/pom.xml clean package

#
# Package stage
#
FROM openjdk:11-jre-slim
COPY --from=build /home/user-service/target/user-service-0.0.1.jar /usr/local/lib/app.jar
EXPOSE 9002
ENTRYPOINT ["java","-jar","/usr/local/lib/app.jar"]

#docker build -t shopfront . 
#docker run -dp 8010:8010 shopfront


#kubectl apply -f shopfront-service.yaml