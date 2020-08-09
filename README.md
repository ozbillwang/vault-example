# A quick sample to run Vault in Kubernetes

### Prerequisite

- `kubernetes cluster` - it can be minikube, kops, kubernetes from Docker for Mact, kubeadm, and so on.
- `kubectl` - https://kubernetes.io/docs/tasks/tools/install-kubectl/
- `helm chart` - https://helm.sh/
- `kubectx` - Faster way to switch between clusters and namespaces in kubectl (https://github.com/ahmetb/kubectx - Connect to preview )
- `helm diff` - A helm plugin that shows a diff explaining what a helm upgrade would change (https://github.com/databus23/helm-diff - Connect to preview )
- `k9s` - https://github.com/derailed/k9s - Connect to preview 

Installation
```
brew install kubectl 
brew install helm
brew install kubectx
brew install k9s

helm plugin install https://github.com/databus23/helm-diff
```

### reference: 

https://learn.hashicorp.com/tutorials/vault/kubernetes-minikube?in=vault/kubernetes
