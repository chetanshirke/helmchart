# Create deployment
``` 
helm install webapp-release webapp/ --values webapp/values.yaml
```
# Create Kubernetes secrets for database
```
kubectl --namespace {{ .Values.namespace}} create secret generic webapp-secret --from-literal=DB-PASSWORD=YOUR-PASSWORD
```
# Expose port if running on minikube cluster
```
kubectl --namespace {{ .Values.namespace}} port-forward service/ 80:808
```