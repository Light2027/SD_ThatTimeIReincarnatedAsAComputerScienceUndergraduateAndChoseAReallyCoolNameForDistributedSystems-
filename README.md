# Links
https://minikube.sigs.k8s.io/docs/handbook/accessing/#using-minikube-tunnel
https://www.youtube.com/watch?v=K4uNl6JA7g8
https://kubernetes.io/docs/tasks/inject-data-application/define-environment-variable-container/

## GitHub
https://github.com/Light2027/SD_ThatTimeIReincarnatedAsAComputerScienceUndergraduateAndChoseAReallyCoolNameForDistributedSystems-

## Azure DevOps
https://dev.azure.com/112966/Uebung

## Azure Kubernetes Service API URL
uebung-dns-c122e23c.hcp.westeurope.azmk8s.io

# Process
Here we first created the docker file. Then, after some testing of course, we built it and pushed it to the registry for testing purposes using the following commands.
```console
docker build -t istvan1997/node:latest .
docker push istvan1997/node:latest
```

After which we created the kubernetes files a config and deployment file.
```console
kubectl apply -f node-config.yaml
kubectl apply -f node.yaml
```
We then tested these using minikube, where the commented observation was made.
```console 
minikube service --url node-service # For NodePort-s only
minikube tunnel # For LoadBalancers => Here one have to set the LoadBalancers port to something beyond 1000 to use it with minikube
```

Finally it was time to use Azure DevOps and deploy our application to Azure. 
Istvan was choosen as the host, as he had the highest balance remaining.
So Azure apparently wants you to use the Azure Container Registry, so Istvan had to create one.
Then Istvan deleted his Kubernetes cluster, and created a new one for this project.
Afterwards we noticed there was already a template available for the pipelines that builds the image, pushes it to the registry, and finally deploys it to the Azure Kubernetes Cluster, so we gave it a try.
Apparently you don't need the Kubernetes files, so those were deleted and the newly created yaml files adjusted.
Azure could not find my config file so it was removed and the yaml files adjusted.
After that it worked, but still adjusted the ports so that the app uses port **80** instead of **8080**.
See images folder.