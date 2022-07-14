#
# Build stage
#
FROM maven:3.6.0-jdk-11-slim AS build
COPY src /home/hystrix-dashboard/src	
COPY pom.xml /home/hystrix-dashboard
RUN mvn -f /home/hystrix-dashboard/pom.xml clean package

#
# Package stage
#
FROM openjdk:11-jre-slim
COPY --from=build /home/hystrix-dashboard/target/hystrix-dashboard-0.0.1.jar /usr/local/lib/app.jar
EXPOSE 9295
ENTRYPOINT ["java","-jar","/usr/local/lib/app.jar"]

#docker build -t shopfront . 
#docker run -dp 8010:8010 shopfront


#kubectl apply -f shopfront-service.yaml