# initcontainer-example-01-kubernetes
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: pod1
  labels:
    app: v1.0.0
spec:
  containers:
  - name: pod1
    image: nginx:latest
    imagePullPolicy: IfNotPresent
  initContainers:
  - name: init1
    image: busybox:latest
    command: ['sh', '-c', "sleep 15"]
```
```
kubectl apply -f init.yaml
```
