# opensearch-deployment

## installation

* `git clone https://github.com/averykhoo/opensearch-deployment.git`
  * `git submodule update --init --recursive`
  * `git submodule update --recursive`
* https://opensearch.org/docs/opensearch/install/helm/
  * `helm package opensearch-devops/Helm/opensearch`
  * `helm install -f os-values.yaml os opensearch-1.0.0.tgz`
* https://opensearch.org/docs/dashboards/install/helm/
  * `helm package opensearch-devops/Helm/opensearch-dashboards`
  * `helm install -f osd-values.yaml osd opensearch-dashboards-1.0.0.tgz`
* https://opensearch.org/docs/clients/logstash/index/
  * ~~helm install -f ls-values.yaml ls helm/elastic/logstash~~
  * `kubectl create configmap logstash-conf --from-file logstash-development/logstash.conf`
  * `kubectl apply -f logstash-deployment/app.yaml`
  *

# todo

* tolerations and node selectors