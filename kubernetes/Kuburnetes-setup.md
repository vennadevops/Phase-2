
Reference: https://kubernetes.io/docs/getting-started-guides/ubuntu/installation/

# Launch an AWS Ubuntu machine and login as route user.

# 1. Add the cloud & credentials

  * Command: juju add-credential aws

        Output:

        root@ip-172-31-2-89:~# juju add-credential aws
        Enter credential name: my_aws_creds

        Using auth-type "access-key".

        Enter access-key: AKIA********EVTOIQ


        Enter secret-key:

        Credential "my_aws_creds" added locally for cloud "aws".

#2. Create an instance on AWS EC2. A new instance will be created in AWS with the instance name 'juju-controller-machine-0' and machine type t2.medium.

	* Command: juju bootstrap aws/us-east-2
	
	Output:
		root@ip-172-31-2-89:~# juju bootstrap aws/us-east-2
		Creating Juju controller "aws-us-east-2" on aws/us-east-2
		Looking for packaged Juju agent version 2.4.0 for amd64
		Launching controller instance(s) on aws/us-east-2...
		 - i-029ce605929c7924e (arch=amd64 mem=4G cores=2)us-east-2a"
		Installing Juju agent on bootstrap instance
		Fetching Juju GUI 2.13.2
		Waiting for address
		Attempting to connect to 172.31.10.23:22 #Private ip
		Attempting to connect to 18.191.254.105:22 #public ip
		Connected to 18.191.254.105
		Running machine configuration script...
		Bootstrap agent now started
		Contacting Juju controller at 18.191.254.105 to verify accessibility...
		Bootstrap complete, "aws-us-east-2" controller now available
		Controller machines are in the "controller" model
		Initial model "default" added

	
# 3. Launch a Kubernetes cluster

	juju deploy canonical-kubernetes

	Output:

	Located bundle "cs:bundle/canonical-kubernetes-218"
	Resolving charm: cs:~containers/easyrsa-50
	Resolving charm: cs:~containers/etcd-96
	Resolving charm: cs:~containers/flannel-66
	Resolving charm: cs:~containers/kubeapi-load-balancer-69
	Resolving charm: cs:~containers/kubernetes-master-122
	Resolving charm: cs:~containers/kubernetes-worker-138
	Executing changes:
	- upload charm cs:~containers/easyrsa-50 for series xenial
	- deploy application easyrsa on xenial using cs:~containers/easyrsa-50
	  added resource easyrsa
	- set annotations for easyrsa
	- upload charm cs:~containers/etcd-96 for series xenial
	- deploy application etcd on xenial using cs:~containers/etcd-96
	  added resource etcd
	  added resource snapshot
	- set annotations for etcd
	- upload charm cs:~containers/flannel-66 for series xenial
	- deploy application flannel on xenial using cs:~containers/flannel-66
	  added resource flannel-amd64
	  added resource flannel-arm64
	  added resource flannel-s390x
	- set annotations for flannel
	- upload charm cs:~containers/kubeapi-load-balancer-69 for series xenial
	- deploy application kubeapi-load-balancer on xenial using cs:~containers/kubeapi-load-balancer-69
	- expose kubeapi-load-balancer
	- set annotations for kubeapi-load-balancer
	- upload charm cs:~containers/kubernetes-master-122 for series xenial
	- deploy application kubernetes-master on xenial using cs:~containers/kubernetes-master-122
	  added resource cdk-addons
	  added resource kube-apiserver
	  added resource kube-controller-manager
	  added resource kube-scheduler
	  added resource kubectl
	- set annotations for kubernetes-master
	- upload charm cs:~containers/kubernetes-worker-138 for series xenial
	- deploy application kubernetes-worker on xenial using cs:~containers/kubernetes-worker-138
	  added resource cni-amd64
	  added resource cni-arm64
	  added resource cni-s390x
	  added resource kube-proxy
	  added resource kubectl
	  added resource kubelet
	- expose kubernetes-worker
	- set annotations for kubernetes-worker
	- add relation kubernetes-master:kube-api-endpoint - kubeapi-load-balancer:apiserver
	- add relation kubernetes-master:loadbalancer - kubeapi-load-balancer:loadbalancer
	- add relation kubernetes-master:kube-control - kubernetes-worker:kube-control
	- add relation kubernetes-master:certificates - easyrsa:client
	- add relation etcd:certificates - easyrsa:client
	- add relation kubernetes-master:etcd - etcd:db
	- add relation kubernetes-worker:certificates - easyrsa:client
	- add relation kubernetes-worker:kube-api-endpoint - kubeapi-load-balancer:website
	- add relation kubeapi-load-balancer:certificates - easyrsa:client
	- add relation flannel:etcd - etcd:db
	- add relation flannel:cni - kubernetes-master:cni
	- add relation flannel:cni - kubernetes-worker:cni
	- add unit easyrsa/0 to new machine 0
	- add unit etcd/0 to new machine 1
	- add unit etcd/1 to new machine 2
	- add unit etcd/2 to new machine 3
	- add unit kubeapi-load-balancer/0 to new machine 4
	- add unit kubernetes-master/0 to new machine 5
	- add unit kubernetes-master/1 to new machine 6
	- add unit kubernetes-worker/0 to new machine 7
	- add unit kubernetes-worker/1 to new machine 8
	- add unit kubernetes-worker/2 to new machine 9
	Deploy of bundle completed.

![image](https://user-images.githubusercontent.com/24622526/44193393-2d8d6000-a122-11e8-8515-541f9dcf80f8.png)

![image](https://user-images.githubusercontent.com/24622526/44193680-32064880-a123-11e8-875a-dc13cfc362a5.png)

