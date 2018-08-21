Ex-2:

kubectl get nodes >>>> Check whether the node is read or not.

kubectl get pods >>> check is there any pod available on the nodes.

1. Creating a Deployment:

	kubectl create -f  https://k8s.io/examples/controllers/nginx-deployment.yaml
	
	kubectl get nodes >>> check whether the pods created or not for this deployment.
