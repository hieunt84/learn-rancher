### setup rancher in k8s using helm
### Ref
    https://rancher.com/docs/rancher/v2.x/en/installation/install-rancher-on-k8s/
    https://artifacthub.io/packages/helm/rancher-stable/rancher

### Info Setup
    https://rancher.my.org
    admin/password@2021

### Setup
    helm repo add rancher-stable https://releases.rancher.com/server-charts/stable

    kubectl create namespace cattle-system
    ...
    helm install rancher rancher-stable/rancher \
      --namespace cattle-system \
      --set hostname=rancher.my.org

    kubectl -n cattle-system rollout status deploy/rancher
    kubectl -n cattle-system get deploy rancher
    minikube addons enable ingress