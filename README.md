# argocd-demo

# 1. Install argoCD 

kubectl create namespace argocd
kubectl apply -n argocd --server-side --force-conflicts -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

kubectl  port-forward -n argocd  svc/argocd-server 8080:443

http://127.0.0.1:8080
username :admin
pwd :   > kubectl get secret -n argocd
kubectl get secret  argocd-initial-admin-secret -n argocd -o yaml

[System.Text.Encoding]::UTF8.GetString([System.Convert]::FromBase64String("eGI3SUpXU1BsbXVlMTJCcg=="))

eGI3SUpXU1BsbXVlMTJCcg==

# Attach argocd to container

kubectl apply -f application.yaml

pruning:

kubectl edit deployment -n myapp myapp-deployment

kubectl create secret docker-registry dockerhub-cred --docker-server=https://index.docker.io/v1/  --docker-username=xxxxx --docker-password= --docker-email=xx@test.com -n myapp
