# Monitoring
Monitoring services for Nova Microservices

This guide assumes that K8s is already installed and running. A recommended option is [minikube](https://minikube.sigs.k8s.io/docs/start/).

## Namespace
Create a namespace first.

`kubectl create namespace monitoring`

## Deploying to K8s
Apply the all deployment files. This command will search recursively for all the nested deployment files.

`kubectl apply -f k8s\ -R`

## Getting the pod name
Get the monitoring pods.

`kubectl get pods --namespace=monitoring`

## Port forwarding
Port forward Grafana to access it.

`kubectl port-forward -n monitoring grafana-<pod-id here> 3001:3000`

## Grafana dashboard setup
You will be prompted to login. The default username is admin and the default password is admin. You will be prompted with the option to change it, however this isn't neccesary. You can click on skip.

Choose the default prometheus provider.

On the top left side click on dashboard icon > import and use the json file provided in the root of the project. Click on import.

Your dashboard has been created. Congratulations!
