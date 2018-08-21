Reference: https://kubernetes.io/docs/concepts/workloads/controllers/deployment/

* Once the master and nodes are available run the below commands one by one abd try to understand:

* Command: kubectl get nodes >>>> Check whether the node is read or not.

![image](https://user-images.githubusercontent.com/24622526/44384284-3360b800-a50b-11e8-97ff-abfd52052106.png)


* Command: kubectl get pods >>> check is there any pod available on the nodes.

### Step-1. Creating a Deployment:

	kubectl create -f  https://k8s.io/examples/controllers/nginx-deployment.yaml
	
	kubectl get nodes >>> check whether the pods created or not for this deployment.

Result of the recently triggered commands.

![image](https://user-images.githubusercontent.com/24622526/44384307-4d9a9600-a50b-11e8-8db7-bb9044001179.png)
