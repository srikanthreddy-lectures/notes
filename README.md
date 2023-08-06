# notes

kubectl delete pods,services,deployments --all
kubectl get pods,services,deployments

kubectl get configmaps kube-dns -o yaml 

kubectl exec --stdin --tty <<pod>> -- /bin/bash

1.20.5

https://github.com/srikanthreddy-lectures/k8_react_front_back_end.git

dnsPolicy: ClusterFirstWithHostNet

sudo usermod -aG docker $USER && newgrp docker
minikube start --network-plugin=cni --cni=calico

kubectl -n default edit svc frontend-service

kubectl port-forward --address 0.0.0.0 frontend-service 80:80
kubectl port-forward --address 0.0.0.0 service/frontend-service 31699:80


git clone https://github.com/srikanthreddy-lectures/realgrande-backend2023.git
cd realgrande-backend2023/

sudo nano Dockerfile
FROM node
WORKDIR /app
COPY . /app
RUN npm install
CMD ["npm","start"]
EXPOSE 3002

sudo docker build -t rg2 .
sudo docker tag rg2:latest scott2srikanth/rg2-backend:latest
sudo docker login
sudo docker push scott2srikanth/rg2-backend:latest

cd ..

git clone https://github.com/srikanthreddy-lectures/k8_react_front_back_end.git
cd k8_react_front_back_end

sudo nano backend-deployment.yaml

minikube tunnel

kubectl create -f backend-deploy.yaml 
kubectl get svc

kubectl port-forward --address 0.0.0.0 service/backend-service 3002:3002
