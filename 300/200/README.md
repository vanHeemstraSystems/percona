# 200 - Prerequisites

Before getting started with Percona Everest, do the following:

1. Install [curl](https://everything.curl.dev/get). **NOTE**: Curl is already installed on GitPod.
2. Set up a Kubernetes cluster. Percona Everest assists with installing all the necessary operators and required packages, but does not currently help with spinning up a Kubernetes cluster. We recommend setting up Percona Everest on the Amazon Elastic Kubernetes Service (EKS) or Google Kubernetes Engine (GKE).

## 100 - Create Kubernetes cluster on Amazon Elastic Kubernetes Service (EKS)

See [README.md](./100/README.md)

## 200 - Create Kubernetes cluster on Google Kubernetes Engine (GKE)

See [README.md](./200/README.md)

## 300 - Install on Render.com (Our Choice)

See [README.md](./300/README.md)

3. Verify the you have accewss to Kubernetes cluster that you want to use with Everest. By default, Everest uses the kubeconfig file available under ```~/.kube/config```. To verify access to the Kubernetes cluster, run the following command: ```$ kubectl get nodes```. Expected output: ```NAME                                    STATUS   ROLES    AGE   VERSION
gke-<name>-default-pool-75d48bfc-bx8g   Ready    <none>   11h   v1.26.7-gke.500
gke-<name>-default-pool-75d48bfc-c2df   Ready    <none>   11h   v1.26.7-gke.500
gke-<name>-default-pool-75d48bfc-zl7k   Ready    <none>   11h   v1.26.7-gke.500```
