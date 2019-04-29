In this step we will inspect the chart.

## Task

Update dependencies

`helm dependency update lets-chat`{{execute}}

`tree lets-chat`{{execute}}

Inspect

`helm inspect lets-chat`{{execute}}

Examine a chart for possible issues

`helm lint lets-chat`{{execute}}

Simulate installation

`helm install lets-chat --name demo -f my_values.yml --debug --dry-run`{{execute}}
