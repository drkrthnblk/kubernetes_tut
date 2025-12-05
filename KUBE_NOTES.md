## create cluster
kind create cluster --name `<cluster_name>`

kind create cluster --name cka-cluster1

## create cluster with config file
kind create cluster --name `<cluster_name>` --config `<yaml_file>`

kind create cluster --name cka-cluster2 --config config.yml

## get cluster details
### kind will create a cluster with "kind-" prefix
kubectl cluster-info --context `<cluster_name>`

kubectl cluster-info --context kind-cka-cluster1

## list all nodes
kubectl get nodes 

## list all nodes with extra info
kubectl get nodes -o wide

## get all context/cluster
kubectl config get-context

## switching the context/cluster
kubectl config use-context `<cluster_name>`

kubectl config use-context kind-cka-cluster1

# Replication sets

## create replication set from yaml file

kubectl apply -f `<yaml_file>`

kubectl apply -f replication_replicaset.yml 

## get all running pods
kubectl get po

## get all replication sets/ replication controllers
kubectl get rc

## delete replication set

kubeclt delete rc/`<replication_set_name>`

kubeclt delete rc/ngnix-replication-controller

## declerative way to scale up/ down pods

kubectl `scale` --replicas=2 rs/`<replication_set_name>`

kubectl scale --replicas=2 rs/ngnix-replication-set

## create deployment

kubectl apply -f `<yaml_file>` 

kubectl apply -f deployment.yml


## update deployment to use a new image
## this will do a rolling update on on containers/pods

kubectl `set image` deploy/`<deployment_name>` `<container_name>`=`<container_name>`:`<new_version_of_image>`

kubectl set image deploy/ngnix-deployment ngnix-container=ngnix-container:1.9.1

## get last 2 deployment history

kubectl `rollout history` deploy/`<deployment_name>`

kubectl rollout history deploy/ngnix-deployment

## rollback a deployment

kubectl `rollout undo` deploy/`<deployment_name>`

kubectl rollout undo deploy/ngnix-deployment  