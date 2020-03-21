# hello-node docker image
docker/build:
	docker build -t hello-minikube/hello-node .

docker/push:
	docker login
	docker tag hello-minikube/hello-node karahiyo4docker/hello-minikube
	docker push karahiyo4docker/hello-minikube

# Deployment
kubectl/deployment:
	kubectl create deployment hello-node --image=docker.io/karahiyo4docker/hello-minikube

kubectl/get-deployments:
	kubectl get deployments

kubectl/get-pods:
	kubectl get pods

kubectl/get-events:
	kubectl get events

kubectl/config-view:
	kubectl config view


# Service
kubectl/expose:
	kubectl expose deployment hello-node --type=LoadBalancer --port=8080

kubectl/get-services:
	kubectl get services

minikube/service:
	minikube service hello-node

# clean up
__cleanup: 
	kubectl delete service hello-node
	kubectl delete deployment hello-node

__stop/minikube:
	minikube stop

__delete/minikube:
	minikube delete

