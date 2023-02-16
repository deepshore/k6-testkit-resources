# k6-testkit-resources
A condensed demo setup of everything you need to get k6 running seriously on k8s

# what you will need

## optimal 

- all of minimal
- the permission to install the (k6-operator)[https://github.com/grafana/k6-operator]
- javascript amateur
- minimal knowledge about handling dashboard and visualizations in kibana
- some degree of experience with loadtesting and expectations

## minimal

- a running kubernetes system and the usual suspects of tools. our recommendation: [rancher-desktop](https://docs.rancherdesktop.io/getting-started/installation/)
- [k6 installed](https://k6.io/docs/get-started/installation/)
- the ability and permission to create at least a namespace and install resources via helm charts. 
- a minimal understanding of javascript notation (read)

# get started

## optimal way

- install elasticsearch via 
  - `kubectl create -f https://download.elastic.co/downloads/eck/2.6.1/crds.yaml` and
  - `kubectl apply -f https://download.elastic.co/downloads/eck/2.6.1/operator.yaml` 
- import the saved objects located in [kibana folder](kibana/export.ndjson)
- create a namespace `kubectl create ns k6demo`
- switch context `kubectl config set-context --current --namespace k6demo`
- `kubectl apply -f resources/`
- done. your test is running.
- check with `watch kubectl get k6 k6-test-by-deepshore` for completion
- check the K6 Loadtest by Deepshore Dashboard in kibana.