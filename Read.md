
https://learnk8s.io/spring-boot-kubernetes-guide
/mnt/c/WorkSpace/K8POC

	• docker build -t poc-k8 .
	• docker images
	• docker ps
	• docker run \
	    --name=poc-k8-v2 \
		○ -p 8080:8080  \
		○ poc-k8
	• docker login
	• docker tag poc-k8 veenu143/poc-k8-java:1.0.0
	• docker push veenu143/poc-k8-java:1.0.0
	• docker run \
	   --name=poc-k8-v2 \
	   -p 8080:8080  \
	  veenu143/poc-k8-java:1.0.0
	• docker stop poc-k8-v3

Kubernetes
https://kubernetes.io/docs/reference/kubectl/cheatsheet/
	• kubectl cluster-info
	• kubectl apply -f kube
	• kubectl get pods --watch
	• minikube service knote --url
	• kubectl scale --replicas=2 deployment/poc-k8-kube
	• kubectl get pods -l app=knote --watch
	•  kubectl apply -f kube/k8-poc-service.yaml
	• kubectl get services --watch
