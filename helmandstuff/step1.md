In this step you will deploy kubernetes dashboard and connect to it

## Task

Deploying the dashboard:

`kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/master/aio/deploy/recommended/kubernetes-dashboard.yaml | bash`{{execute}}

Enable the UI access:

`kubectl proxy | bash`{{execute}}