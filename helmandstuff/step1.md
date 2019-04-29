In this step you will deploy kubernetes dashboard and connect to it

## Task

Deploying the dashboard:

`kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/master/aio/deploy/recommended/kubernetes-dashboard.yaml`{{execute}}

You can check the status of the pods by executing:

`kubectl get pods --all-namespaces`

you should see eventally all pods up and running:

```
NAMESPACE     NAME                                    READY     STATUS    RESTARTS   AGE
kube-system   coredns-78fcdf6894-d49dl                1/1       Running   0          5m
kube-system   coredns-78fcdf6894-vwp45                1/1       Running   0          5m
kube-system   etcd-master                             1/1       Running   0          4m
kube-system   kube-apiserver-master                   1/1       Running   0          4m
kube-system   kube-controller-manager-master          1/1       Running   0          4m
kube-system   kube-proxy-z2tbm                        1/1       Running   0          5m
kube-system   kube-scheduler-master                   1/1       Running   0          4m
kube-system   kubernetes-dashboard-5dd89b9875-sw5d4   1/1       Running   0          5m
kube-system   weave-net-nwx7q                         2/2       Running   1          5m
```

Enable the UI access:

`kubectl proxy`{{execute}}

Browse and check out kubernetes dashboard:

https://[[HOST_SUBDOMAIN]]-8001-[[KATACODA_HOST]].environments.katacoda.com/api/v1/namespaces/kube-system/services/https:kubernetes-dashboard:/proxy/.
