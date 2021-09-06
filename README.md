# opensearch-deployment

## installation

* `git clone https://github.com/averykhoo/opensearch-deployment.git`
  * `git submodule update --init --recursive`
  * `git submodule update --recursive`
* https://opensearch.org/docs/opensearch/install/helm/
  * `helm package opensearch-devops/Helm/opensearch`
  * `helm install -n default -f os-values.yaml os opensearch-1.0.0.tgz`
  * `helm install -n default -f os-values.yaml --set replicas=1 os opensearch-1.0.0.tgz`
* https://opensearch.org/docs/dashboards/install/helm/
  * `helm package opensearch-devops/Helm/opensearch-dashboards`
  * `helm install -n default -f osd-values.yaml osd opensearch-dashboards-1.0.0.tgz`
* https://opensearch.org/docs/clients/logstash/index/
  * ~~helm install -n default -f ls-values.yaml ls helm/elastic/logstash~~
  * `kubectl -n default create configmap logstash-conf --from-file logstash-development/logstash.conf`
  * `kubectl -n default apply -f logstash-deployment/app.yaml`
  *

# todo

* tolerations and node selectors
* how to insert the pem files? 
  * https://opensearch.org/docs/security-plugin/configuration/generate-certificates/
* how to use envoy and opa with kibana
* do i need envoy and opa with elastic too?