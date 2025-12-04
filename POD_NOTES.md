## pod creation imperative way
kubectl run `<pod_name>` --image=`<image_name>`:`<image_version>`

kubectl run nginx-pod --image=nginx:latest

## pod creation declerative way
kubectl create -f `<yaml_file_name>`

kubectl create -f declerative_pod.yml

## show error on pod creation/ details of running pod
kubectl describe pod `<pod_name>`

kubectl describe pod ngnix-pod

## edit running pod metadata directly
kubectl edit pod `<pod_name>`

kubectl edit pod ngnix-pod

## exec in to a pod
kubectl exec -it `<pod_name>` -- sh

kubectl exec -it ngnix-pod -- sh

## create yaml from pod
### dry-run doesn't apply the changes
kubectl run `<pod_name>` --image=`<iamge_name>` --dry-run=client -o yaml > pod.yml

kubectl run ngnix-pod --image=ngnix --dry-run=client -o yaml > pod.yml

## pod deletion
kubectl delete pod `<pod_name>`

kubectl delete pod nginx-pod

## get pod metadata fields for running pod
kubectl explain pod

## show labels of pod
kubectl get pods `<pod_name>` --show-labels

kubectl get pods ngnix-pod --show-labels