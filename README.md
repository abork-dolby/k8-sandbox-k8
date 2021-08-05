## Cluster bootstraping
https://www.arthurkoziel.com/setting-up-argocd-with-helm/


Manually install ArgoCD using Helm chart
```
helm repo add argo-cd https://argoproj.github.io/argo-helm
helm dep update charts/argo-cd/
helm install argo-cd charts/argo-cd/
```

Install the root ArgoCD app the "app of apps"
```
helm template apps | k apply -f -
```


Access ArgoCD UI from your laptop
```
kubectl port-forward svc/argo-cd-argocd-server 8080:443
```
Reset admin password by following this guide
https://github.com/argoproj/argo-cd/blob/master/docs/faq.md#i-forgot-the-admin-password-how-do-i-reset-it