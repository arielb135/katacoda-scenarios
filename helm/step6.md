In this step we will add graphs to dashboard.

## Task

Install heapster - which will allow us to get metrics

`helm install --name heapster --namespace kube-system --set service.nameOverride=heapster stable/heapster`{{execute}}

Deploying the dashboard:

`kubectl apply -f https://gist.githubusercontent.com/mjboxboat/9601f7aff786f52bce3f4af7e21b8339/raw/572f1c056c9385fb5ebc8a55a64717331028b284/kube-dash.yml`{{execute}}

You can check the status of the pods by executing:

`kubectl get pods -n kube-system`{{execute}}

you should see eventally all pods up and running:

```
NAME                                    READY     STATUS    RESTARTS   AGE
coredns-78fcdf6894-9wt7h                1/1       Running   0          47s
coredns-78fcdf6894-dqxf6                1/1       Running   0          47s
kube-proxy-9hgxj                        1/1       Running   0          47s
kubernetes-dashboard-57584d8594-sdwts   1/1       Running   0          38s
weave-net-tkl5m                         2/2       Running   1          47s
```

Browse and check out kubernetes dashboard, go to the "demo" namespace and check out the objects:

https://[[HOST_SUBDOMAIN]]-32000-[[KATACODA_HOST]].environments.katacoda.com	
