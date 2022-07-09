# week8-kubernetes-helm

gcloud container clusters get-credentials my-gke-cluster

helm install my-nginx-ingress nginx/nginx-ingress --version 0.13.2 -n nginx-cert-manager

helm install my-cert-manager cert-manager/cert-manager --version 1.8.2 -n nginx-cert-manager

kubectl apply -f cluster-issuer.yaml -n nginx-cert-manager

kubectl apply -f .\probe.yaml

helm install my-kube-prometheus-stack prometheus-community/kube-prometheus-stack --version 36.2.1 -n kube-grafana -f .\values-kube-prometheus-stack.yaml

helm install my-prometheus-blackbox-exporter prometheus-community/prometheus-blackbox-exporter --version 5.8.2 -n kube-grafana

helm install my-skooner christianknell/skooner --version 0.0.3 -n dashboard-skooner -f .\values-skooner.yaml

kubectl get secrets -n dashboard-skooner
kubectl -n dashboard-skooner describe secret my-skooner-token-tfxp8

helm install my-deploy-website my-deploy-week4 -n my-website