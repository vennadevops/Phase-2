# Running Kubernetes Locally via Minikube


https://github.com/aws-samples/aws-workshop-for-kubernetes/blob/master/03-path-application-development/301-local-development/readme.adoc


ex-1:
kubectl run nginx-deployment --image=nginx --port=80

kubectl expose deployment nginx-deployment --port=80 --type=NodePort

kubectl get svc nginx-deployment

ex-2:
kubectl run devops-deployment --image=venkatasykam/devopswebapp:1.0.13 --port=8080

kubectl expose deployment devops-deployment --port=8080 --type=NodePort

kubectl get svc devops-deployment


