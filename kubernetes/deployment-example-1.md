Reference: https://kubernetes.io/docs/concepts/workloads/controllers/deployment/

* Once the master and nodes are available run the below commands one by one and try to understand:

* Command: kubectl get nodes >>>> Check whether the node is read or not.

![image](https://user-images.githubusercontent.com/24622526/44384284-3360b800-a50b-11e8-97ff-abfd52052106.png)


* Command: kubectl get pods >>> check is there any pod available on the nodes.

## Step-1. Creating a Deployment:

	kubectl create -f  https://k8s.io/examples/controllers/nginx-deployment.yaml
	
	kubectl get nodes >>> check whether the pods created or not for this deployment.


* Result of the recently executed 3 commands.

![image](https://user-images.githubusercontent.com/24622526/44384307-4d9a9600-a50b-11e8-8db7-bb9044001179.png)

	kubectl get deployments
	
![image](https://user-images.githubusercontent.com/24622526/44384444-bb46c200-a50b-11e8-8176-bea54248a04d.png)

#### When you inspect the Deployments in your cluster, the following fields are displayed:

* NAME lists the names of the Deployments in the cluster.
* DESIRED displays the desired number of replicas of the application, which you define when you create the Deployment. This is the desired state.
* CURRENT displays how many replicas are currently running.
* UP-TO-DATE displays the number of replicas that have been updated to achieve the desired state.
* AVAILABLE displays how many replicas of the application are available to your users.
* AGE displays the amount of time that the application has been running.

* Check the statu of deployment: kubectl rollout status deployment/nginx-deployment

![image](https://user-images.githubusercontent.com/24622526/44384682-85560d80-a50c-11e8-89a6-3610b17aa320.png)

* To see the ReplicaSet (rs) created by the deployment, run the command: kubectl get rs:

![image](https://user-images.githubusercontent.com/24622526/44384751-bcc4ba00-a50c-11e8-81c8-30ed320f9aaf.png)

* Notice that the name of the ReplicaSet is always formatted as [DEPLOYMENT-NAME]-[POD-TEMPLATE-HASH-VALUE]. The hash value is automatically generated when the Deployment is created.

* To see the labels automatically generated for each pod, run the command "kubectl get pods --show-labels". The following output is returned:

![image](https://user-images.githubusercontent.com/24622526/44384844-10370800-a50d-11e8-9cd5-8382b17684c9.png)

* The created ReplicaSet ensures that there are three nginx Pods running at all times.
