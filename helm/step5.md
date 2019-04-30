In this task we will enable text files upload, while the application is still in air.

## Task

Edit the values yaml, and enable the files support

`demo/lets-chat/values.yaml`{{open}}

Change files_support enabled to ** true **:

```
# Should we support file upload?	
files_support:
  enabled: false
```

Upgrade the chart:

`helm upgrade demo -f ./lets-chat/values.yaml ./lets-chat`{{execute}}

Check out that the pods are indeed re-created, note that the sha256 helped doing so as changing a configMap doesn't tell the deployment to restart:

`kubectl get pods -n demo`{{execute}}

Open the application again and see that now you are able to upload files

http://[[HOST_SUBDOMAIN]]-30303-[[KATACODA_HOST]].environments.katacoda.com

You can play with the values (to allow / disallow text files or images and upgrade again)

Let's say that the upgrade was unsuccessful from your end, let's rollback the change, see now that the files are not allowed:

`helm history demo`{{execute}}

`helm rollback demo 1`{{execute}}
