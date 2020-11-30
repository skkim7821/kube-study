sudo apt-get update
sudo apt-get install docker.io
sudo systemctl enable docker
sudo systemctl status docker
sudo systemctl start docker

curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add

sudo apt-add-repository "deb http://apt.kubernetes.io/ kubernetes-xenial main"
sudo apt-get install kubeadm kubelet kubectl
sudo apt-mark hold kubeadm kubelet kubectl

sudo swapoff –a

sudo hostnamectl set-hostname master-node
sudo hostnamectl set-hostname worker01


### master node
sudo kubeadm init --pod-network-cidr=10.244.0.0/16
mkdir -p $HOME/.kube
sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
sudo chown $(id -u):$(id -g) $HOME/.kube/config

sudo kubectl apply -f https://raw.githubusercontent.com/coreos/flannel/master/Documentation/kube-flannel.yml
kubectl get pods --all-namespaces


### workers
sudo kubeadm join


### master node
kubectl get nodes

brew install derailed/k9s/k9s 
brew install helm

helm repo add haproxytech https://haproxytech.github.io/helm-charts
helm repo update
helm install kubernetes-ingress haproxytech/kubernetes-ingress