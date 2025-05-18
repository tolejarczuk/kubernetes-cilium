# Cilium project

Upgrade cilium install with these settings:

```sh
helm upgrade cilium cilium/cilium --version 1.17.4\
   --namespace kube-system\
   --set prometheus.enabled=true\
   --set operator.prometheus.enabled=true\
   --set hubble.enabled=true\
   --set hubble.relay.enabled=true\
   --set hubble.ui.enabled=true\
   --set hubble.metrics.enableOpenMetrics=true\
   --set hubble.metrics.enabled="{dns,drop,tcp,flow,port-distribution,icmp,httpV2:exemplars=true;labelsContext=source_ip\,source_namespace\,source_workload\,destination_ip\,destination_namespace\,destination_workload\,traffic_direction}"
```
