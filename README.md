# microservice-protocol-mngt

Sample how micro-services can manage external & internal protocols with different versions

# Pre-requisites

* Kubernetes (use `minikube` for local development)

* [Istio with mutual TLS authentication](https://istio.io/docs/setup/kubernetes/quick-start/)

* GoLang (1.11.x)

* Docker

#### Installing Istio

1) Install

```bash
kubectl apply -f ext/isto/crds.yaml
kubectl apply -f ext/isto/istio.yaml
```

2) Check installation 

```bash
kubectl get pods -n istio-system
```

Sample output:

```bash
NAME                                     READY   STATUS      RESTARTS   AGE
istio-citadel-5bbbc98c6d-4wftr           1/1     Running     0          3m14s
istio-cleanup-secrets-4sm4l              0/1     Completed   0          3m15s
istio-egressgateway-77dfd495df-cz5k9     1/1     Running     0          3m14s
istio-galley-744969c89-2z85v             1/1     Running     0          3m14s
istio-ingressgateway-6bb7555c76-kt5rw    1/1     Running     0          3m14s
istio-pilot-6cbbb9bd95-582sp             2/2     Running     0          3m14s
istio-policy-755477988-7rp9r             2/2     Running     0          3m14s
istio-security-post-install-dhrzb        0/1     Completed   4          3m15s
istio-sidecar-injector-856b74c95-xhllp   1/1     Running     0          3m14s
istio-telemetry-78f76f9d6-m5dkf          2/2     Running     0          3m14s
prometheus-65d6f6b6c-7vpww               1/1     Running     0          3m14s
```