# gcp_with_sb_app

helm install app .
helm install app1 . --set container.image=mikhailyesman/sbifk8s:2.0 --set replicaCount=2
helm install app2 . --set container.image=mikhailyesman/sbifk8s:3.0 --set replicaCount=1
helm install app2 . --set container.image=mikhailyesman/sbifk8s:lts --set replicaCount=3

helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
helm repo update
helm install ingress-nginx ingress-nginx/ingress-nginx

helm install app .
kubectl apply -f ingress.yaml
kubectl describe ingress
kubectl get ingress
kubectl describe ingress
