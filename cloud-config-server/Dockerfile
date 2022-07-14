#
# Build stage
#
FROM maven:3.6.0-jdk-11-slim AS build
COPY src /home/cloud-config-server/src	
COPY pom.xml /home/cloud-config-server
RUN mvn -f /home/cloud-config-server/pom.xml clean package

#
# Package stage
#
FROM openjdk:11-jre-slim
COPY --from=build /home/cloud-config-server/target/cloud-config-server-0.0.1.jar /usr/local/lib/app.jar
EXPOSE 9296
ENTRYPOINT ["java","-jar","/usr/local/lib/app.jar"]

#docker build -t shopfront . 
#docker run -dp 8010:8010 shopfront


#kubectl apply -f shopfront-service.yaml