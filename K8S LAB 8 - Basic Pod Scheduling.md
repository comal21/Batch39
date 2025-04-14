# Task 1 : Get Node Label 
## List the worker nodes 
```
kubectl get nodes
```
## Set label to one of the worker node 
```
kubectl label nodes <worker-node-name> role=node
```
## View worker nodes and their labels
```
kubectl get nodes --show-labels | grep role=node
```
# Task 2 : Create a pod and use nodeName to constrain it to a particular node
## Create a YAML file named nlns-pod1.yaml with the following content:
```
vi nlns-pod1.yaml
```
```
apiVersion: v1
kind: Pod
metadata:
  name: nlns-nginx-pod1
  labels:
    env: test
spec:
  containers:
  - name: nlns-nginx-ctr
    image: nginx
  nodeName: <worker-node-name>
```
## Save and exit the editor
## Apply the nlns-pod1.yaml created in the previous step
```
kubectl apply -f nlns-pod1.yaml
```
## Verify Pod Scheduling
```
kubectl get pods -o wide
```
# Task 3 : Create a pod and use nodeSelestor to constrain it to a particular node
## Create a YAML file named nlns-pod2.yaml with the following content:

```
vi nlns-pod1.yaml
```
```
apiVersion: v1
kind: Pod
metadata:
  name: nlns-nginx-pod2
  labels:
    env: test
spec:
  containers:
  - name: nlns-nginx-ctr
    image: nginx
  nodeSelector:
      role: node
```
## Save and exit the editor
## Apply the nlns-pod2.yaml created in the previous step
```
kubectl apply -f nlns-pod2.yaml
```
## Verify Pod Scheduling
```
kubectl get pods -o wide
```



