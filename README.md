# Links
https://minikube.sigs.k8s.io/docs/handbook/accessing/#using-minikube-tunnel

```console
docker build -t istvan1997/node:latest .
docker push istvan1997/node:latest
```

```console
kubectl apply -f node-config.yaml
kubectl apply -f node.yaml
```

```console 
minikube service --url node-service # For NodePort-s only
minikube tunnel # For LoadBalancers => Here one have to set the LoadBalancers port to something beyond 1000 to use it with minikube
```

git init
git add .
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/Light2027/SD_ThatTimeIReincarnatedAsAComputerScienceUndergraduateAndChoseAReallyCoolNameForDistributedSystems-.git
git push -u origin main