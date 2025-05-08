# repo

```
kind create cluster --config=kind-config.yaml
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/kind/deploy.yaml
kubectl edit svc ingress-nginx-controller -n ingress-nginx
helm repo add jetstack https://charts.jetstack.io
helm repo update
helm upgrade --install cert-manager jetstack/cert-manager --namespace cert-manager --create-namespace --version v1.15.3 --set crds.enabled=true
kubectl apply -f clusterissuer.yaml -n cert-manager
helm repo add jenkins https://charts.jenkins.io
helm repo update
helm upgrade --install jenkins jenkins/jenkins --create-namespace -n jenkins -f jenkins-values.yaml
```
