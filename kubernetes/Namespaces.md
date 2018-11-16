# Namespaces

Refer: 
https://kubernetes.io/docs/concepts/overview/working-with-objects/namespaces/

https://kubernetes.io/docs/tasks/administer-cluster/namespaces-walkthrough/

kubectl get namespaces

            root@k8s-master:~# kubectl get namespaces
            NAME          STATUS   AGE
            default       Active   5m28s
            kube-public   Active   5m28s
            kube-system   Active   5m28s
            root@k8s-master:~#
            
       * default The default namespace for objects with no other namespace
       
       * kube-system The namespace for objects created by the Kubernetes system
       
       * kube-public This namespace is created automatically and is readable by all users (including those not authenticated). This namespace is mostly reserved for cluster usage, in case that some resources should be visible and readable publicly throughout the whole cluster. The public aspect of this namespace is only a convention, not a requirement.
       
kubectl create namespace [namespace-name]

ex-1: kubectl create namespace dev

ex-2: kubectl create namespace qa

ex-3: kubectl create namespace prod

ex-4: kubectl create namespace webserver


