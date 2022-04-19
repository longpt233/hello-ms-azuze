## hello-k8s-azuze
deploy golang app on cloud


## overview



## install k8s cluster

### create user

- tạo su user cho k8s

```aidl
sudo adduser longpt  
sudo usermod -aG sudo longpt
sudo mkdir /home/longpt/.ssh
sudo vi /home/longpt/.ssh/authorized_keys
```

- host

```aidl

```

### install k8s

1. cài docker cho các node

```aidl
sudo apt-get install docker.io
sudo usermod -aG docker longpt
```

2. cai k8s

```aidl
sudo curl -fsSLo /usr/share/keyrings/kubernetes-archive-keyring.gpg https://packages.cloud.google.com/apt/doc/apt-key.gpg
echo "deb [signed-by=/usr/share/keyrings/kubernetes-archive-keyring.gpg] https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee /etc/apt/sources.list.d/kubernetes.list
sudo apt-get update
sudo apt-get install -y kubelet kubeadm kubectl  .. 
```

- server loi vl


### minikube


```
$ wget https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
$ sudo cp minikube-linux-amd64 /usr/local/bin/minikube
$ sudo chmod +x /usr/local/bin/minikube
$ minikube version
minikube version: v1.21.0
commit: 76d74191d82c47883dc7e1319ef7cebd3e00ee11
$ curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl
$ chmod +x kubectl
$ sudo mv kubectl /usr/local/bin/
$ kubectl version -o yaml
$ minikube start --driver=docker
```
