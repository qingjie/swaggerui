```
helm repo add cetic https://cetic.github.io/helm-charts
helm repo update
helm install swaggerui cetic/swaggerui -n swaggerui -f values.yaml
```
1. delete old configmap like the following:
```
kubectl delete configmap swaggerui --namespace swaggerui
```
2. create new configmap like the following(pls rename your json file to conf.json):
```
kubectl create configmap swaggerui --namespace swaggerui --from-file=conf.json
```
3. delete pod to reload new configmap like the following:
```
kubectl get all -n swaggerui
kubectl delete pod/swaggerui-***** -n swaggerui
```


