# EFK-SSO-KubernetesLogs
EFK on Linux collect Kubernetes logs and Link Kibana and SSO(KeyCloak) 

1. Installation<br>
  a. Install Opendistro for Elasticsearch : https://opendistro.github.io/for-elasticsearch-docs/docs/install/rpm/<br>
  b. Install Opendistro for Elasticsearch-kibana : https://opendistro.github.io/for-elasticsearch-docs/docs/kibana/<br>
  c. Install Fluentd : https://docs.fluentd.org/installation/install-by-rpm<br>
  <br><br>
2. SSO<br>
  a. Refer to KeyCloakSSOSettings/files<br>
  b. Reset Elasticsearch config and Kibana config<br> 
  <br><br>
3. Fluentd<br>
  fluentd receive logs using forward tag (24224port) and send elastic search (9200port)<br>
  Refer to Fluentd/td-agent.conf<br>
  <br><br>
4. Fluent-bit<br>
  you deploy daemonset fluent-bit so fluent-bit pods as many as k8s nodes will collect logs of all pods on all nodes.<br>
  your fluent-bit collects metadata as well as logs.<br>
  Refer to Fluent-bit/files and 'kubectl apply -f files'
