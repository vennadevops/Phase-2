### two containers in a single pod

kubectl create -f [nginx-service.yml](yml/nginx-service.yml)

kubectl get all -o wide

kubectl describe pod [pod-name]

kubectl exec -it [pod-name] -- bin/bash

find / -name "nginx" 

find / -name "jenkins"

Ctrl + p + q

kubectl exec -it [pod-name] -c jenkins-container -- bin/bash

cd /var/jenkins_home/

Ctrl + p + q

kubectl exec -it [pod-name] -c nginx-container -- bin/bash

cd /usr/share/nginx/html

Ctrl + p + q

kubectl cp [source] [pod-name]:[container-path] -c [container-name]

kubectl cp sample.html jen-nginx-deployment-6dc6c78687-5h8hr:/usr/share/nginx/html/ -c nginx-container

kubectl exec [pod-name] -c nginx-container ls /usr/share/nginx/html/

kubectl expose deployment.apps/jen-nginx-deployment --type=NodePort

kubectl get all (or) kubectl get svc

http://[public-ip]:[nginx-node-port]

http://[public-ip]:[jenkins-node-port]




