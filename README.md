# Horizontal-Autoscaling-Kubernetes
Horizontal Autoscaling Kubernetes based on CPU usage


kubectl get po -n kube-system
kubectl apply -f components.yaml

kubectl apply -f deploy.yaml
kubectl get pods

kubectl autoscale deployment hpa-deployment --cpu-percent=50 --min=1 --max=4
kubectl get hpa

kubectl apply -f pod.yaml
kubectl exec mybox -it -- /bin/sh

while true; do wget -q -O- http://php-apache; done

kubectl get hpa

kubectl delete hpa hpa-deployment
kubectl delete -f pod.yaml --grace0period=0 --force
kubectl delete -f deploy.yaml

kubectl delete -f components.yaml