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
coredns-78fcdf6894-b5wwz                1/1       Running   0          12m
coredns-78fcdf6894-mwjsw                1/1       Running   0          12m
etcd-master                             1/1       Running   0          11m
heapster-heapster-84bfbd79d-cn6jd       2/2       Running   0          19s
kube-apiserver-master                   1/1       Running   0          11m
kube-controller-manager-master          1/1       Running   0          12m
kube-proxy-wsvx8                        1/1       Running   0          12m
kube-scheduler-master                   1/1       Running   0          11m
kubernetes-dashboard-57584d8594-lnhkc   1/1       Running   0          19s
tiller-deploy-7c69c66d57-7kvgj          1/1       Running   0          12m
weave-net-wxcmh                         2/2       Running   1          12m
```

Browse and check out kubernetes dashboard, go to the "demo" namespace and check out the objects:

https://[[HOST_SUBDOMAIN]]-32000-[[KATACODA_HOST]].environments.katacoda.com	
