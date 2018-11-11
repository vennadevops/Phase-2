Reference: 

https://kubernetes.io/docs/concepts/overview/components/

https://www.aquasec.com/wiki/display/containers/Kubernetes+Architecture+101


![image](https://user-images.githubusercontent.com/24622526/48311050-48575f80-e5bf-11e8-85db-0bab51f91c9e.png)


Master Componets:

etcd - a simple, distributed key value storage which is used to store the Kubernetes cluster data (such as number of pods, their state, namespace, etc), API objects and service discovery details.

kube-apiserver: Kubernetes API server is the central management entity that receives all REST requests for modifications (to pods, services, replication sets/controllers and others), serving as frontend to the cluster. Also, this is the only component that communicates with the etcd cluster, making sure data is stored in etcd and is in agreement with the service details of the deployed pods.

kubectl: is a command line tool that interacts with kube-apiserver and send commands to the master node. Each command is converted into an API call.

controller-manager: 

      kube-controller-manager - runs a number of distinct controller processes in the background (for example, replication controller controls number of replicas in a pod, endpoints controller populates endpoint objects like services and pods, and others) to regulate the shared state of the cluster and perform routine tasks. When a change in a service configuration occurs (for example, replacing the image from which the pods are running, or changing parameters in the configuration yaml file), the controller spots the change and starts working towards the new desired state.
      
      cloud-controller-manager - is responsible for managing controller processes with dependencies on the underlying cloud provider (if applicable). For example, when a controller needs to check if a node was terminated or set up routes, load balancers or volumes in the cloud infrastructure, all that is handled by the cloud-controller-manager.


kube-scheduler: Component on the master that watches newly created pods that have no node assigned, and selects a node for them to run on.


Node Componets:

kubelet: the main service on a node, regularly taking in new or modified pod specifications (primarily through the kube-apiserver) and ensuring that pods and their containers are healthy and running in the desired state. This component also reports to the master on the health of the host where it is running.

kebe-proxy: a proxy service that runs on each worker node to deal with individual host subnetting and expose services to the external world. It performs request forwarding to the correct pods/containers across the various isolated networks in a cluster.

Container Runtime: The container runtime is the software that is responsible for running containers. Kubernetes supports several runtimes: Docker, rkt, runc and any OCI runtime-spec implementation.


-----

pod:
generally refers to one or more containers that should be controlled as a single application. A pod encapsulates application containers, storage resources, a unique network ID and other configuration on how to run the containers.




