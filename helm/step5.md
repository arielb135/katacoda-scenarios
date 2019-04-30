In this task we will enable text files upload, while the application is still in air.

## Task

Edit the values yaml, and enable the 

`values.yaml`{{open}}

`helm install lets-chat --name demo --namespace demo -f values.yml`{{execute}}

List releases

`helm list`{{execute}}

Check deployment status

`helm status demo`{{execute}}

`kubectl get pods -n demo`{{execute}}

Open application, Register and open chat - see that indeed files are not allowed (right pane)

http://[[HOST_SUBDOMAIN]]-30303-[[KATACODA_HOST]].environments.katacoda.com

Delete database pod and relogin to see that the data was preserved

`kubectl delete pod -n demo -l app=demo-mongodb`{{execute}}
