# Running Kubernetes Locally via Minikube


https://github.com/aws-samples/aws-workshop-for-kubernetes/blob/master/03-path-application-development/301-local-development/readme.adoc

### Install docker.

Launahc an EC2 ubuntu instance. And connect to it, then install docker.

sudo -i

apt-get update -y &&  apt-get install -y docker.io

### Install minikube

curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 && chmod +x minikube && sudo mv minikube /usr/local/bin/

minikube version

### Install kubectl

curl -Lo kubectl https://storage.googleapis.com/kubernetes-release/release/v1.8.0/bin/linux/amd64/kubectl && chmod +x kubectl && sudo mv kubectl /usr/local/bin/

source <(kubectl completion bash)

### Start minukube - single node cluster setup

minikube start --vm-driver=none

minikube status

### Deploy docker images

ex-1:
kubectl run nginx-deployment --image=nginx --port=80

kubectl expose deployment nginx-deployment --port=80 --type=NodePort

kubectl get svc nginx-deployment

ex-2:
kubectl run devops-deployment --image=venkatasykam/devopswebapp:1.0.13 --port=8080 --replicas=2

kubectl expose deployment devops-deployment --port=8181 --target-port=8080 --type=NodePort

kubectl get svc devops-deployment


docker ps

kubectl get nodes

kubectl describe node <node-name>

Kubernetes dashboard - Monitor the deployments: http://18.212.188.134:30000

minikube stop


