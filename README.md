# spring-native-image

Spring GraalVM native image as a Function in k8s (Minikube) with Fission

- Serverless deployed with [fission.io](https://fission.io/)

#### Minikube

Make sure Minikube is running.

```bash
docker build -t spring-native-image .
```

```bash
minikube image load spring-native-image
```

#### Fission

Make sure Fission CLI is installed and running.

```bash
fission version && fission check
```

```bash
fission fn run-container --name hello --image spring-native-image
```

```bash
fission route create --name hello-route --function hello --prefix /hello --keepprefix
```

```bash
fission fn test --name hello --method GET --subpath /hello 
```
