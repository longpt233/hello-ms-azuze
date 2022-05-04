## tạo cụm 

- chú ý node pools để 1 thôi k tốn tiền 
- kết quả : long-group và aks group 

![](./asset/long-group.png)

![](./asset/aks-group.png)

# kết nối cụm với gitlab ci

- ref: https://stackoverflow.com/questions/50749095/how-to-integrate-gitlab-ci-w-azure-kubernetes-kubectl-acr-for-deployments

- lấy thông tin, điền vô project> infratructure> kubenettes cluster 

```
cat .kube/config 
name: long-k8s-cluster-name
server: API URL
certificate-authority-data : CA Certificate -> dùng base64 decode cái này
token: 
```
- chú ý cái scope để điền vô env của gitlab-ci -> lấy biễn $KUBECONFIG

- kết quả 

![](/asset/gitlab-connect-k8s.png)


# cách trên nỗi quá phải dùng cách mới thôi 

- ref: https://docs.gitlab.com/ee/user/infrastructure/clusters/migrate_to_gitlab_agent.html

- connect to cluster

```
helm repo add gitlab https://charts.gitlab.io
helm repo update
helm upgrade --install gitlab-agent gitlab/gitlab-agent \
    --namespace gitlab-agent \
    --create-namespace \
    --set config.token=PRFjzNv7hHsTghKxkcDdc1yyaSWiBNuttcnhb3p1PkT_-x-ZLg \
    --set config.kasAddress=wss://kas.gitlab.com
```

- kết quả

![](/asset/connect-new.png)

