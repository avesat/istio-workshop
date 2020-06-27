#### Run ISTIO in minikube
```
minikube start --memory=8192 --cpus=2
```

```
istioctl install --set profile=demo
```

```
kubectl label namespace default istio-injection=enabled
```

```
kubectl apply -f k8s/
```

```
kubectl apply -f gateway.yaml
```

```
kubectl apply -f destination-rules.yaml
```

```
kubectl apply -f destination-rules-chuck.yaml
```

```
kubectl apply -f request-routing.yaml
```

```
kubectl apply -f request-routing-chuck.yaml
```

```
kubectl get all --all-namespaces
```

```
kubectl port-forward svc/istio-ingressgateway 8088:80 -n istio-system
```

```
kubectl -n istio-system apply -f attribute_gen_service.yaml
```

```
kubectl -n istio-system get envoyfilter stats-filter-1.6 -o yaml > stats-filter-1.6.yaml
```

```
kubectl -n istio-system apply -f stats-filter-1.6.yaml
```

```
http://localhost:8088/
```

```
minikube delete
```
