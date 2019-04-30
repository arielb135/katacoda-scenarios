In this step we will deploy and maintain life cycle of the application.

## Task

Install the chart

`helm install lets-chat --name demo --namespace demo -f ./lets-chat/values.yaml`{{execute}}

List releases

`helm list`{{execute}}

Check deployment status

`helm status demo`{{execute}}

`kubectl get pods -n demo`{{execute}}

Open application, Register and open chat - see that indeed files are not allowed (right pane)

** Note - There's issue in chrome with this app, open in internet explorer or firefox **

http://[[HOST_SUBDOMAIN]]-30303-[[KATACODA_HOST]].environments.katacoda.com

Delete database pod and relogin to see that the data was preserved

`kubectl delete pod -n demo -l app=demo-mongodb`{{execute}}
