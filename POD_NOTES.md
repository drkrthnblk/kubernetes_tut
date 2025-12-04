## pod creation imperative way
kubectl run <span style="color:blue">&lt;pod_name&gt;</span> --image=<span style="color:blue">&lt;image_name&gt;</span>:<span style="color:blue">&lt;image_version&gt;</span>

kubectl run nginx-pod --image=nginx:latest

## pod creation declerative way
kubectl create -f <span style="color:blue">&lt;yaml_file_name&gt;</span>

kubectl create -f declerative_pod.yml

## show error on pod creation/ details of running pod
kubectl describe pod <span style="color:blue">&lt;pod_name&gt;</span>

kubectl describe pod ngnix-pod

## edit running pod metadata directly
kubectl edit pod <span style="color:blue">&lt;pod_name&gt;</span>

kubectl edit pod ngnix-pod

## exec in to a pod
kubectl exec -it <span style="color:blue">&lt;pod_name&gt;</span> -- sh

kubectl exec -it ngnix-pod -- sh

## create yaml from pod
### dry-run doesn't apply the changes
kubectl run <span style="color:blue">&lt;pod_name&gt;</span> --image=<span style="color:blue">&lt;iamge_name&gt;</span> --dry-run=client -o yaml > pod.yml

kubectl run ngnix-pod --image=ngnix --dry-run=client -o yaml > pod.yml

## pod deletion
kubectl delete pod <span style="color:blue">&lt;pod_name&gt;</span>

kubectl delete pod nginx-pod

## get pod metadata fields for running pod
kubectl explain pod

## show labels of pod
kubectl get pods <span style="color:blue">&lt;pod_name&gt;</span> --show-labels

kubectl get pods ngnix-pod --show-labels