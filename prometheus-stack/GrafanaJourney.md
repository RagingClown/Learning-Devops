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