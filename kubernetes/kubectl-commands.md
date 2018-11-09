### kubectl-commands

* create the deployments/pods/containers

  kubectl create deployment [delployment-name] --image=[docker-image-name]
  
* create the service to expose the app

  kubectl create service [port-type]  [delployment-name] --tcp=8080:8080
  
* run the specific container

  kubectl run [deployment-name] --image=jenkins --replicas=2 --port=8080 --hostport=8888

* list the pods/nodes/deployments/services

  kubectl get pods/pod/nodes/node/deploy/deployments/services/svc

* list the pods/nodes/deployments/services by name

  kubectl get pods/pod/nodes/node/deploy/deployments/services/svc [name]

* description(information) of the pods/nodes/deployments/services

  kubectl describe pods/pod/nodes/node/deploy/deployments/services/svc [name]

* delete pods/nodes/deployments/services

  kubectl delete pods/pod/nodes/node/deploy/deployments/services/svc [name] 
  
  or
  
  kubectl delete pods/pod/nodes/node/deploy/deployments/services/svc [name] --force
  
* kubectl logs [pod name]

* 


  
  
