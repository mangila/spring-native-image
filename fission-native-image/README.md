# spring-native-image

Spring GraalVM native image as a Fission Function in k8s (Minikube)

Beneficial for ease of deployment and scaling.

- Serverless deployed with [fission.io](https://fission.io/)

#### Minikube

Make sure Minikube is running.

```bash
docker build -t fission-native-image .
```

```bash
minikube image load fission-native-image
```

#### Fission

Make sure Fission CLI is installed and running.

```bash
fission version && fission check
```

```bash
fission fn run-container --name hello --image fission-native-image
```

```bash
fission route create --name hello-route --function hello --prefix /hello --keepprefix
```

```bash
fission fn test --name hello --method GET --subpath /hello 
```
