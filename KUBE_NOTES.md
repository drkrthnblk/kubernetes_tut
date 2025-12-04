## create cluster
kind create cluster --name <span style="color:blue">&lt;cluster_name&gt;</span>
kind create cluster --name cka-cluster1

## create cluster with config file
kind create cluster --name <span style="color:blue">&lt;cluster_name&gt;</span> --config <span style="color:blue">&lt;yaml_file&gt;</span>
kind create cluster --name cka-cluster2 --config config.yml

## get cluster details
### kind will create a cluster with "kind-" prefix
kubectl cluster-info --context <span style="color:blue">&lt;cluster_name&gt;</span>
kubectl cluster-info --context kind-cka-cluster1

## list all nodes
kubectl get nodes 

## list all nodes with extra info
kubectl get nodes -o wide

## get all context/cluster
kubectl config get-context

## switching the context/cluster
kubectl config use-context <span style="color:blue">&lt;cluster_name&gt;</span>
kubectl config use-context kind-cka-cluster1