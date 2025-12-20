# spring-native-image

Spring GraalVM native image as a Job in K8s (Minikube)

Beneficial for one of the tasks.

#### Minikube

Make sure Minikube is running.

```bash
docker build -t job-native-image .
```

```bash
minikube image load job-native-image
```

```bash
kubectl apply -f job-k8s.yaml
```

```bash
kubectl apply -f scheduled-k8s.yaml
```
