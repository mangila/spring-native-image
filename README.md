# spring-native-image

Spring GraalVM native image as FaaS in k8s

Spring native image compile

- Serverless deployed with [fission.io](https://fission.io/)

#### Fission

```bash
docker build -t spring-native-image .
```

```bash
fission fn run-container --name hello --image spring-native-imagefission route create --name hello-route --function hello --prefix /hello --keepprefix --port 8888
```

```bash
fission route create --name hello-route --function hello --prefix /hello --keepprefix
```
