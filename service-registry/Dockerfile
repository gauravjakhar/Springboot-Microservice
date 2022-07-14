#
# Build stage
#
FROM maven:3.6.0-jdk-11-slim AS build
COPY src /home/service-registry/src	
COPY pom.xml /home/service-registry	
RUN mvn -f /home/service-registry/pom.xml clean package

#
# Package stage
#
FROM openjdk:11-jre-slim
COPY --from=build /home/service-registry/target/service-registry-0.0.1.jar /usr/local/lib/app.jar
EXPOSE 8761
ENTRYPOINT ["java","-jar","/usr/local/lib/app.jar"]

#docker build -t shopfront . 
#docker run -dp 8010:8010 shopfront


#kubectl apply -f shopfront-service.yaml