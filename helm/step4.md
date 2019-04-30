In this step we will deploy and maintain life cycle of the application.

## Task

Install the chart

`helm install lets-chat --name demo --namespace demo -f my_values.yml`{{execute}}

List releases

`helm list`{{execute}}

Check deployment status

`helm status demo`{{execute}}

`kubectl get pods -n demo`{{execute}}

Upgrade applicattion

`sed -i 's/0.4.7/0.4.6/g' lets-chat/Chart.yaml`{{execute}}

`helm upgrade demo lets-chat --set replicas=2`{{execute}}

Rollback

`helm history demo`{{execute}}

`helm rollback demo 1`{{execute}}

Open application

http://[[HOST_SUBDOMAIN]]-30303-[[KATACODA_HOST]].environments.katacoda.com

Delete database pod and relogin to see that the data was preserved

`kubectl delete pod -n demo -l app=demo-mongodb`{{execute}}
