In this step we will inspect the chart.

## Task

Update dependencies

`helm dependency update lets-chat`{{execute}}

`tree lets-chat`{{execute}}

Inspect, see that the dependency of "MongoDB" was created.

`helm inspect lets-chat`{{execute}}

Examine a chart for possible issues

`helm lint lets-chat`{{execute}}

Simulate installation

`helm install lets-chat --name demo -f my_values.yml --debug --dry-run`{{execute}}

** Note ** - When you want to test the template rendering, but not actually install anything, you can use helm install --debug --dry-run ./mychart. This will send the chart to the Tiller server, which will render the templates. But instead of installing the chart, it will return the rendered template to you so you can see the output
