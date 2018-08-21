Reference: https://kubernetes.io/docs/concepts/workloads/controllers/deployment/

* Once the master and nodes are available run the below commands one by one and try to understand what is happening:

* Command: kubectl get nodes >>>> Check whether the nodes are ready or not.

![image](https://user-images.githubusercontent.com/24622526/44387273-986cdb80-a514-11e8-9137-3fc57f55858a.png)

* Command: kubectl get pods or kubectl get pod >>> check is there any pod available on the nodes.

## Step-1. Creating a Deployment:

	kubectl create -f  https://k8s.io/examples/controllers/nginx-deployment.yaml
	
	kubectl get nodes or kubectl get node >>> check whether the pods created or not for this deployment.

* Result of the recently executed 3 commands.

![image](https://user-images.githubusercontent.com/24622526/44384307-4d9a9600-a50b-11e8-8db7-bb9044001179.png)

* command: kubectl get deployments (or) kubectl get deploy
	
![image](https://user-images.githubusercontent.com/24622526/44384444-bb46c200-a50b-11e8-8176-bea54248a04d.png)

* deployment info: 

	* describe all the deployments: kubectl describe deploy
	* describe a deployment: kubectl describe deploy nginx-deployment

![image](https://user-images.githubusercontent.com/24622526/44387015-cbfb3600-a513-11e8-9be6-f2a250127d27.png)

* All pods: kubectl get pods

![image](https://user-images.githubusercontent.com/24622526/44387420-01545380-a515-11e8-9a6f-f839a217f148.png)

* describe pods: 

	* describe all the pods: kubectl describe pods
	* describe a single pod: kubectl describe pods/<pod-name>  (we can find an info related on which ndoe this pod is running)

![image](https://user-images.githubusercontent.com/24622526/44387618-87709a00-a515-11e8-855c-bfd9b37e5724.png)

* All nodess: kubectl get nodes

* describe nodes: 

	* decribe all the nodes: kubectl describe nodes
	* describe a single node: kubectl describe nodes <node-name>  (we can find an info what are all the pods are running in each node)

			root@k-master:~# kubectl get nodes
			NAME       STATUS    ROLES     AGE       VERSION
			k-master   Ready     master    28m       v1.11.2
			k-node-1   Ready     <none>    23m       v1.11.2
			k-node-2   Ready     <none>    11m       v1.11.2
			root@k-master:~# kubectl describe nodes k-node-1
			Name:               k-node-1
			Roles:              <none>
			Labels:             beta.kubernetes.io/arch=amd64
					    beta.kubernetes.io/os=linux
					    kubernetes.io/hostname=k-node-1
			Annotations:        kubeadm.alpha.kubernetes.io/cri-socket=/var/run/dockershim.sock
					    node.alpha.kubernetes.io/ttl=0
					    volumes.kubernetes.io/controller-managed-attach-detach=true
			CreationTimestamp:  Tue, 21 Aug 2018 07:21:36 +0000
			Taints:             <none>
			Unschedulable:      false
			Conditions:
			  Type                 Status  LastHeartbeatTime                 LastTransitionTime                Reason                       Message
			  ----                 ------  -----------------                 ------------------                ------                       -------
			  NetworkUnavailable   False   Tue, 21 Aug 2018 07:21:49 +0000   Tue, 21 Aug 2018 07:21:49 +0000   WeaveIsUp                    Weave pod has set this
			  OutOfDisk            False   Tue, 21 Aug 2018 07:44:38 +0000   Tue, 21 Aug 2018 07:21:36 +0000   KubeletHasSufficientDisk     kubelet has sufficient disk space available
			  MemoryPressure       False   Tue, 21 Aug 2018 07:44:38 +0000   Tue, 21 Aug 2018 07:21:36 +0000   KubeletHasSufficientMemory   kubelet has sufficient memory available
			  DiskPressure         False   Tue, 21 Aug 2018 07:44:38 +0000   Tue, 21 Aug 2018 07:21:36 +0000   KubeletHasNoDiskPressure     kubelet has no disk pressure
			  PIDPressure          False   Tue, 21 Aug 2018 07:44:38 +0000   Tue, 21 Aug 2018 07:21:36 +0000   KubeletHasSufficientPID      kubelet has sufficient PID available
			  Ready                True    Tue, 21 Aug 2018 07:44:38 +0000   Tue, 21 Aug 2018 07:21:56 +0000   KubeletReady                 kubelet is posting ready status. AppArmor enabled
			Addresses:
			  InternalIP:  172.31.46.154
			  Hostname:    k-node-1
			Capacity:
			 cpu:                1
			 ephemeral-storage:  15181020Ki
			 hugepages-2Mi:      0
			 memory:             1014516Ki
			 pods:               110
			Allocatable:
			 cpu:                1
			 ephemeral-storage:  13990828009
			 hugepages-2Mi:      0
			 memory:             912116Ki
			 pods:               110
			System Info:
			 Machine ID:                 e8d61eaba5954831a078e7af8def0c46
			 System UUID:                EC24C848-CF74-AD85-144A-67EF0652213E
			 Boot ID:                    c33360d8-e69e-42cd-a352-026bf0799a27
			 Kernel Version:             4.4.0-1061-aws
			 OS Image:                   Ubuntu 16.04.4 LTS
			 Operating System:           linux
			 Architecture:               amd64
			 Container Runtime Version:  docker://17.3.2
			 Kubelet Version:            v1.11.2
			 Kube-Proxy Version:         v1.11.2
			Non-terminated Pods:         (5 in total)
			  Namespace                  Name                                 CPU Requests  CPU Limits  Memory Requests  Memory Limits
			  ---------                  ----                                 ------------  ----------  ---------------  -------------
			  default                    nginx-deployment-67594d6bf6-8z5qq    0 (0%)        0 (0%)      0 (0%)           0 (0%)
			  default                    nginx-deployment-67594d6bf6-fp6vj    0 (0%)        0 (0%)      0 (0%)           0 (0%)
			  default                    nginx-deployment-67594d6bf6-wwvzx    0 (0%)        0 (0%)      0 (0%)           0 (0%)
			  kube-system                kube-proxy-8g277                     0 (0%)        0 (0%)      0 (0%)           0 (0%)
			  kube-system                weave-net-kgtb6                      20m (2%)      0 (0%)      0 (0%)           0 (0%)
			Allocated resources:
			  (Total limits may be over 100 percent, i.e., overcommitted.)
			  Resource  Requests  Limits
			  --------  --------  ------
			  cpu       20m (2%)  0 (0%)
			  memory    0 (0%)    0 (0%)
			Events:
			  Type    Reason                   Age                From                  Message
			  ----    ------                   ----               ----                  -------
			  Normal  Starting                 23m                kubelet, k-node-1     Starting kubelet.
			  Normal  NodeHasSufficientDisk    23m (x2 over 23m)  kubelet, k-node-1     Node k-node-1 status is now: NodeHasSufficientDisk
			  Normal  NodeHasSufficientMemory  23m (x2 over 23m)  kubelet, k-node-1     Node k-node-1 status is now: NodeHasSufficientMemory
			  Normal  NodeHasNoDiskPressure    23m (x2 over 23m)  kubelet, k-node-1     Node k-node-1 status is now: NodeHasNoDiskPressure
			  Normal  NodeHasSufficientPID     23m (x2 over 23m)  kubelet, k-node-1     Node k-node-1 status is now: NodeHasSufficientPID
			  Normal  NodeAllocatableEnforced  23m                kubelet, k-node-1     Updated Node Allocatable limit across pods
			  Normal  Starting                 23m                kube-proxy, k-node-1  Starting kube-proxy.
			  Normal  NodeReady                22m                kubelet, k-node-1     Node k-node-1 status is now: NodeReady
			root@k-master:~#

#### When you inspect the Deployments in your cluster, the following fields are displayed:

* command: kubectl get deployments or kubectl get deploy

![image](https://user-images.githubusercontent.com/24622526/44384444-bb46c200-a50b-11e8-8176-bea54248a04d.png)


* NAME lists the names of the Deployments in the cluster.
* DESIRED displays the desired number of replicas of the application, which you define when you create the Deployment. This is the desired state.
* CURRENT displays how many replicas are currently running.
* UP-TO-DATE displays the number of replicas that have been updated to achieve the desired state.
* AVAILABLE displays how many replicas of the application are available to your users.
* AGE displays the amount of time that the application has been running.

* Check the statu of deployment: kubectl rollout status deployment/nginx-deployment (or) kubectl rollout status deploy/nginx-deployment

![image](https://user-images.githubusercontent.com/24622526/44384682-85560d80-a50c-11e8-89a6-3610b17aa320.png)

* To see the ReplicaSet (rs) created by the deployment, run the command: kubectl get rs:

![image](https://user-images.githubusercontent.com/24622526/44384751-bcc4ba00-a50c-11e8-81c8-30ed320f9aaf.png)

* Notice that the name of the ReplicaSet is always formatted as [DEPLOYMENT-NAME]-[POD-TEMPLATE-HASH-VALUE]. The hash value is automatically generated when the Deployment is created.

* To see the labels automatically generated for each pod, run the command "kubectl get pods --show-labels". The following output is returned:

![image](https://user-images.githubusercontent.com/24622526/44384844-10370800-a50d-11e8-9cd5-8382b17684c9.png)

* The created ReplicaSet ensures that there are three nginx Pods running at all times.

## Step-2. Updating a Deployment

* Suppose that you now want to update the nginx Pods to use the nginx:1.9.1 image instead of the nginx:1.7.9 image.

* Command: kubectl set image deployment/nginx-deployment nginx=nginx:1.9.1


