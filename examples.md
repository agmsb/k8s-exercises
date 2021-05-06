# Weekly K8s Cert Study Group 

## Controlling Workloads, Pt. II

### General Tips

Get spec for a K8s Pod.
```
kubectl explain pod.spec
```
Get all fields for a K8s Pod.
```
kubectl explain pod.spec --recursive
```

### Labels

Creating a Pod with the label `role=web`.

```
kubectl run nginx --image=nginx --labels role=web
```
Querying all Pods and their respective labels.
```
kubectl get pods --show-labels
```
Query K8s resources with the specific key, `role`.
```
kubectl get pods -L role
```
Add a label to a running Pod.
```
kubectl label pod nginx env=dev
```
Update a Pod's label with the key `env`.
```
kubectl label pod nginx env=prod --overwrite
```
Remove a label with the key `env` from a running Pod.
```
kubectl label pod nginx env-
```

### Annotations

Annotate the Pod with random metadata.
```
kubectl annotate pod nginx some="annotation"
```
Remove the annotation from the Pod with the key `some`.
```
kubectl annotate pod nginx some-
```

### Taint
Taint a Node with `team=ml`.
```
kubectl taint nodes node team=ml:NoSchedule
```
