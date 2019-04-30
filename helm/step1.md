In this step we will prepare Helm tool.

## Task

Download Helm

`curl https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash`{{execute}}

Initialize

`helm init`{{execute}}

Update repository

`helm repo update`{{execute}}

Check all system pods are up

`kubectl get pods -n kube-system`{{execute}}

Check Helm is healthy

`helm version`{{execute}}

### Helm and Tiller

Helm - is a kubernetes package manager, several notes about it:
* Find and use popular software packaged as Helm charts to run in Kubernetes
* Share your own applications as Helm charts
* Create reproducible builds of your Kubernetes applications
* Intelligently manage your Kubernetes manifest files
* Manage releases of Helm packages

Tiller - Tiller is the in-cluster component of Helm. 
It interacts directly with the Kubernetes API server to install, upgrade, query, and remove Kubernetes resources. It also stores the objects that represent releases.