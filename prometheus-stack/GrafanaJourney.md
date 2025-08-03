Kinba my way of learning grafana and prometheous stack with k8s.

Might store some useful stuff here for later.


I'm gonna setup some kind of testing k8s cluster and install kube-prometheus-stack on it to play with grafana. 

For the k8s cluster i'm to try to use kind. If for some reason it's not gonna work as expcted, I'll use k3s setup.

https://www.youtube.com/watch?v=CbkEWcUZ7zM - k3s guide setup.
kube-prometheus-stack youtube guide - https://www.youtube.com/watch?v=fzny5uUaAeY&t=319s

kube-prometheus-stack - https://github.com/prometheus-community/helm-charts/tree/main/charts/kube-prometheus-stack




# commnands


### creating kind cluster

```kind create cluster --config kind-config.yaml --name observability-lab```
```kubectl cluster-info --context kind-observability-lab```


## installing kube prometheus stack

just following the guide there — really easy!

https://github.com/prometheus-community/helm-charts/tree/main/charts/kube-prometheus-stack

A nice way to play with the dashboards and edit them to suit your teams need.


---

root@ubuntu-HP-Elite-SFF-800-G9-Desktop-PC:/home/ubuntu/Desktop/Learning-Devops/prometheus-stack# helm install prometheus prometheus-community/kube-prometheus-stack --namespace monitoring --create-namespace

NAME: prometheus
LAST DEPLOYED: Thu Jul 31 12:48:59 2025
NAMESPACE: monitoring
STATUS: deployed
REVISION: 1
NOTES:
kube-prometheus-stack has been installed. Check its status by running:
  kubectl --namespace monitoring get pods -l "release=prometheus"

Get Grafana 'admin' user password by running:

  kubectl --namespace monitoring get secrets prometheus-grafana -o jsonpath="{.data.admin-password}" | base64 -d ; echo

Access Grafana local instance:

  export POD_NAME=$(kubectl --namespace monitoring get pod -l "app.kubernetes.io/name=grafana,app.kubernetes.io/instance=prometheus" -oname)
  kubectl --namespace monitoring port-forward $POD_NAME 3000

Visit https://github.com/prometheus-operator/kube-prometheus for instructions on how to create & configure Alertmanager and Prometheus instances using the Operator.