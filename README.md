# Monitoring
Monitoring services for Nova Microservices

This guide assumes that K8s is already installed and running.

Create a namespace first.
`kubectl create namespace monitoring`

Apply the all deployment files. This command will search recursively for all the nested deployment files.
`kubectl apply -f k8s\ -R`

Get the monitoring pods.
`kubectl get pods --namespace=monitoring`

Port forward Grafana to access it.
`kubectl port-forward -n monitoring grafana-<pod-id here> 3001:3000`

You will be prompted to login. The default username is admin and the default password is admin. You will be prompted with the option to change it, however this isn't neccesary. You can click on skip.

Choose the default prometheus provider.

On the top left side click on dashboard icon > import and use the json file provided in the root of the project. Click on import.

Your dashboard has been created. Congratulations!
