### kubeadm commands:

kubeadm init

kubeadm join --token [token] [master-ip]:[master-port] --discovery-token-ca-cert-hash sha256:[hash]

kubeadm reset

kubeadm token list

kubeadm token generate

kubeadm token create

kubeadm token create --print-join-command



