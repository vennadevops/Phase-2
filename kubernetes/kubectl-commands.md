### kubectl-commands: https://kubernetes.io/docs/reference/kubectl/overview/

    kubectl [command] [TYPE] [NAME] [flags]

* create the deployments/pods/containers

  kubectl create deployment [delployment-name] --image=[docker-image-name]
  
* create the service to expose the app

  kubectl create service [port-type]  [delployment-name] --tcp=8080:8080
  
* run the specific container

  kubectl run [deployment-name] --image=jenkins --replicas=2 --port=8080 --hostport=8888

* list the pods/nodes/deployments/services

  kubectl get [pods/pod/po]/[nodes/node/no]/[deploy/deployments]/[services/service/svc]

* list the pods/nodes/deployments/services by name

  kubectl get [pods/pod/po]/[nodes/node/no]/[deploy/deployments]/[services/service/svc] [name]

* description(information) of the pods/nodes/deployments/services

  kubectl describe [pods/pod/po]/[nodes/node/no]/[deploy/deployments]/[services/service/svc] [name]

* delete pods/nodes/deployments/services

  kubectl delete [pods/pod/po]/[nodes/node/no]/[deploy/deployments]/[services/service/svc] [name] 
  
  or
  
  kubectl delete [pods/pod/po]/[nodes/node/no]/[deploy/deployments]/[services/service/svc] [name] --force
  
* kubectl logs [pod name]

* kubectl apply:

  ex: kubectl apply -f "https://cloud.weave.works/k8s/net?k8s-version=$(kubectl version | base64 | tr -d '\n')"
  
* kubectl taint: By default, your cluster will not schedule pods on the master for security reasons. If you want to be able to schedule pods on the master, e.g. for a single-machine Kubernetes cluster for development, run below command. This will remove the node-role.kubernetes.io/master taint from any nodes that have it, including the master node, meaning that the scheduler will then be able to schedule pods everywhere.

  ex: kubectl taint nodes --all node-role.kubernetes.io/master-




  
  
