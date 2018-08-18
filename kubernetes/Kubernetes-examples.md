* Reference: https://www.techrepublic.com/article/how-to-quickly-install-kubernetes-on-ubuntu/

* Reference: https://www.cloudtechnologyexperts.com/kubeadm-on-aws/

* https://kubernetes.io/docs/concepts/workloads/controllers/deployment/

* https://kubernetes.io/docs/reference/setup-tools/kubeadm/kubeadm/

* https://kubernetes.io/docs/setup/independent/create-cluster-kubeadm/

* https://kubernetes.io/docs/tasks/debug-application-cluster/get-shell-running-container/

* https://kubernetes.io/docs/reference/kubectl/cheatsheet/

* https://kubernetes.io/docs/concepts/workloads/controllers/deployment/

* https://kubernetes.io/docs/tasks/debug-application-cluster/debug-pod-replication-controller/

* https://kubernetes.io/docs/tasks/administer-cluster/network-policy-provider/kube-router-network-policy/#before-you-begin

* https://github.com/cloudnativelabs/kube-router/blob/master/docs/kubeadm.md

* https://www.digitalocean.com/community/tutorials/how-to-create-a-kubernetes-1-10-cluster-using-kubeadm-on-ubuntu-16-04

* kubectl describe pod `<podName>` | grep IP | awk '{print $2}'


===============================

kubeadm join 172.31.5.56:6443 --token n1n0bx.bvrnur4x81pj02dy --discovery-token-ca-cert-hash sha256:e2ff62d02d77c2ddf1eb21e22e62a3c956bc2f617d983526c83631ac02fe31ef


kubectl run hello-web --image=gcr.io/${PROJECT_ID}/hello-app:v1 --port 8080

kubectl run devopswebapp --image=docker pull venkatasykam/devopswebapp:latest --port 808

kubectl expose deployment nginx-deployment --type=LoadBalancer --port 80 --target-port 8080



kubectl exec my-nginx-59497d7745-rcx2p -- printenv | grep SERVICE


kubectl expose deployment my-nginx --type=LoadBalancer --port 80


Reference: https://kubernetes.io/docs/concepts/services-networking/connect-applications-service/

https://kubernetes.io/docs/concepts/services-networking/service/
https://kubernetes.io/docs/concepts/services-networking/service/
https://kubernetes.io/docs/concepts/cluster-administration/addons/
https://kubernetes.io/docs/tasks/run-application/run-stateless-application-deployment/#creating-and-exploring-an-nginx-deployment
https://kubernetes.io/docs/concepts/services-networking/connect-applications-service/
https://kubernetes.io/docs/tasks/federation/federation-service-discovery/

https://cloud.google.com/kubernetes-engine/docs/tutorials/hello-app

