# Drone Kubernetes Quickstart

A simple drone pipeline that is used to verify the Drone Server installation on Kubernetes

Please check the demo project [Drone on Kubernetes](https://github.com/kameshsampath/drone-on-k8s) for complete end to end setup of Kubernetes on local Kubernetes cluster.


# Drone Kubernetes Quickstart

A simple drone pipeline that is used to verify the Drone Server installation on Kubernetes

Please check the demo project [Drone on Kubernetes](https://github.com/kameshsampath/drone-on-k8s) for complete end to end setup of Kubernetes on local Kubernetes cluster.

> __IMPORTANT__:
  If you are using [KinD](https://kind.sigs.k8s.io/) as your Kubernetes cluster then you might need to update `.drone.yml`  hostAliases to point to the `gitea-http`  __ClusterIP__ otherwise the clone step of the pipeline will fail with `gitea-127.0.0.1.sslip.io` trying to connected local pod container on port`3000`.

  To get the __ClusterIP__ of the `gitea-http` service run the following command,

  ```shell
  kubectl get svc gitea-http -n default -ojsonpath='{.spec.clusterIP}'
```
