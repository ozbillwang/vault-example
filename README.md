# A quick sample to run Vault in Kubernetes

### Prerequisite

- `kubernetes cluster` - it can be minikube, kops, kubernetes from Docker for Mac (or Docker for windows), k3s, kind, kubeadm, rke, eks, ake, gke, and so on.
- `kubectl` - https://kubernetes.io/docs/tasks/tools/install-kubectl/
- `helm chart` - https://helm.sh/
- `kubectx` - Faster way to switch between clusters and namespaces in kubectl (https://github.com/ahmetb/kubectx)
- `helm diff` - A helm plugin that shows a diff explaining what a helm upgrade would change (https://github.com/databus23/helm-diff)
- `k9s` - https://github.com/derailed/k9s

### Install Nginx ingress controller

```
# work in namespace "ingress-nginx"
kubectl create ns ingress-nginx
kubens ingress-nginx

# https://kubernetes.github.io/ingress-nginx/deploy/#docker-for-mac
helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
helm install ingress ingress-nginx/ingress-nginx

# check health
kubectl get services -o wide
```

### Installation on Mac
```
brew install minikube
brew install kubectl 
brew install helm
brew install kubectx
brew install k9s

helm plugin install https://github.com/databus23/helm-diff
```
### Vault installation via helm

Reference: 

https://learn.hashicorp.com/tutorials/vault/kubernetes-minikube?in=vault/kubernetes

### Web application Dockerfile

The author doesn't provide the `Dockerfile` for application image `burtlo/exampleapp-ruby:k8s`, I have reverse engineering it and save the folder [exampleapp-ruby](exampleapp-ruby)

It will be useful to troubleshooting and reference if you can't run the web application properly. 

You can build the image by yourself

```
cd exampleapp-ruby
docker build -t exampleapp-ruby .
```
