

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
	kubectl delete -f .
	
	
AWS
   1. aws ecr create-repository --repository-name demo
   2. aws ecr  get-login --region us-east-1 --no-include-email
   3. docker login -u AWS -p ....
   4. docker tag poc-k8 414795437038.dkr.ecr.us-east-1.amazonaws.com/demo:1.0
   5. docker push 414795437038.dkr.ecr.us-east-1.amazonaws.com/demo:1.0
   6. eksctl create cluster --name demo  --region  us-east-1 --zones us-east-1a,us-east-1b

   
   1.docker build -t 414795437038.dkr.ecr.us-east-1.amazonaws.com/poc-k8:2.0.0 .
   2.docker tag 414795437038.dkr.ecr.us-east-1.amazonaws.com/poc-k8:2.0.0 414795437038.dkr.ecr.us-east-1.amazonaws.com/demo:2.0.0
   3.docker push 414795437038.dkr.ecr.us-east-1.amazonaws.com/demo:2.0.0
   4. kubectl get services --watch
   3.kubectl scale --replicas=2 deployment/poc-k8-kube


AWS CleanUP:
   1. kubectl delete pods
   2. kubectl delete services
   3. eksctl delete cluster --name demo
   4. aws ecr list-images --repository-name demo
   5.aws ecr batch-delete-image --repository-name demo --image-ids
   6. aws ecr delete-repository --repository-name demo --force