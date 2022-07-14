# Springboot-Microservice
Springboot-Microservice

Below to be used for serice registry:
podname-{replica-index}.{serviceName}.default.svc.cluster.local


Use https://github.com/pixel-point/kube-forwarder for port forwarding:

<img width="794" alt="image" src="https://user-images.githubusercontent.com/24937834/178931919-bbfe0b55-4999-4dc5-bd3f-87e110e4b778.png">

or user separate terminal window for each port:

kubectl port-forward service/eureka-lb 8761:80
kubectl port-forward service/cloud-gateway-svc 9191:80
kubectl port-forward service/hystrix-dashboard-svc 9295:80


Build Commands used:
docker build -t jakhardocker/user-service:1.0.0 .

docker build -t jakhardocker/service-registry:1.0.0 .

docker build -t jakhardocker/hystrix-dashboard:1.0.0 .

docker build -t jakhardocker/department-service:1.0.0 .

docker build -t jakhardocker/cloud-gateway:1.0.0 .

docker build -t jakhardocker/cloud-config-server:1.0.0 .


Push commands used:
docker push jakhardocker/user-service:1.0.0

docker push jakhardocker/service-registry:1.0.0

docker push jakhardocker/hystrix-dashboard:1.0.0

docker push jakhardocker/department-service:1.0.0

docker push jakhardocker/cloud-gateway:1.0.0

docker push jakhardocker/cloud-config-server:1.0.0


Microservice Architecture:
<img width="1000" alt="image" src="https://user-images.githubusercontent.com/24937834/178932646-294a222a-94d9-4700-a27f-e97bd71ef656.png">
