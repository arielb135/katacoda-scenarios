In this step we will prepare Helm tool.

## Task

Download Helm

`curl https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash`{{execute}}

Initialize

`helm init`{{execute}}

Update respository

`helm repo update`{{execute}}

Check all system pods are up

`kubectl get pods -n kube-system`{{execute}}

Check Helm is healthy

`helm version`{{execute}}
