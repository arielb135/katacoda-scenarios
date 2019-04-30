In this step we will add graphs to dashboard.

## Task

Install heapster

`helm install --name heapster --namespace kube-system --set service.nameOverride=heapster stable/heapster`{{execute}}

Deploy the dashboard

`kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/master/src/deploy/recommended/kubernetes-dashboard.yaml`{{execute}}

Check pod status

`kubectl get pods -n kube-system`{{execute}}

Once all pods are up, start proxy

`kubectl proxy --address='0.0.0.0' --port=8080 --accept-hosts='^*$'&`{{execute}}

Open the dashboard using URL below

http://[[HOST_SUBDOMAIN]]-8080-[[KATACODA_HOST]].environments.katacoda.com/api/v1/namespaces/kube-system/services/https:kubernetes-dashboard:/proxy/

Use Ctrl+C to stop the proxy

Clean up

`helm delete --purge demo`{{execute}}

`kubectl get pods,deployments,services,rs,cm,pv,pvc -n demo`{{execute}}
