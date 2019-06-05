# Go Application Development with Kubernetes

Welcome to Go Application Development with Kubernetes tutorial!  You can develop
an application without using Kubernetes.  However, if you target to deploy the
application on Kubernetes, there are lots of things to do as an application
developer.  You need to understand the basic concepts like Pod, ReplicaSet,
Deployment, and Service, among others.  You should be familiar with [containers]
to start working with this document.

[containers]: https://docs.docker.com/get-started/

## Getting Started

To setup a Kubernetes cluster locally, you can use [Minikube].

```
curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
chmod +x ./minikube
sudo mv ./minikube /usr/local/bin
```

To start Minikube:

```
minikube start
```

You can install Kubernetes command line tool, [kubectl] like this:

```
curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl
chmod +x ./kubectl
sudo mv ./kubectl /usr/local/bin
```

To see the Kubernetes cluster information:

```
kubectl cluster-info
```

[Minikube]: https://kubernetes.io/docs/tasks/tools/install-minikube/
[kubectl]: https://kubernetes.io/docs/tasks/tools/install-kubectl/

## Pod

Pod YAML (nginx-pod.yaml)::

```
apiVersion: v1
kind: Pod
metadata:
  name: nginx-http-server
  labels:
    app: http-server
spec:
  containers:
  - name: nginx
    image: docker.io/nginx
```


To create pod:

```
kubectl apply -f nginx-pod.yaml
```

You can get the description of the pod like this:

```
$ kubectl describe pod nginx-http-server
Name:               nginx-http-server
Namespace:          default
Priority:           0
PriorityClassName:  <none>
Node:               minikube/192.168.122.205
Start Time:         Wed, 05 Jun 2019 06:07:13 +0530
Labels:             app=http-server
Annotations:        kubectl.kubernetes.io/last-applied-configuration:
                      {"apiVersion":"v1","kind":"Pod","metadata":{"annotations":{},"labels":{"app":"http-server"},"name":"nginx-http-server","namespace":"defaul...
Status:             Running
IP:                 172.17.0.7
Containers:
  nginx:
    Container ID:   docker://d62625eef4e35c66e47ef24aeaad54d9a7f24a25d8ffb396dbdbc9f3c804cf9f
    Image:          docker.io/nginx
    Image ID:       docker-pullable://nginx@sha256:72c584fe83177d622099b786303bf447f19968d82b43c1d41307e0797ab82deb
    Port:           <none>
    Host Port:      <none>
    State:          Running
      Started:      Wed, 05 Jun 2019 06:07:25 +0530
    Ready:          True
    Restart Count:  0
    Environment:    <none>
    Mounts:
      /var/run/secrets/kubernetes.io/serviceaccount from default-token-l56r4 (ro)
Conditions:
  Type              Status
  Initialized       True
  Ready             True
  ContainersReady   True
  PodScheduled      True
Volumes:
  default-token-l56r4:
    Type:        Secret (a volume populated by a Secret)
    SecretName:  default-token-l56r4
    Optional:    false
QoS Class:       BestEffort
Node-Selectors:  <none>
Tolerations:     node.kubernetes.io/not-ready:NoExecute for 300s
                 node.kubernetes.io/unreachable:NoExecute for 300s
Events:
  Type    Reason     Age   From               Message
  ----    ------     ----  ----               -------
  Normal  Scheduled  30s   default-scheduler  Successfully assigned default/nginx-http-server to minikube
  Normal  Pulling    29s   kubelet, minikube  Pulling image "docker.io/nginx"
  Normal  Pulled     18s   kubelet, minikube  Successfully pulled image "docker.io/nginx"
  Normal  Created    18s   kubelet, minikube  Created container nginx
  Normal  Started    18s   kubelet, minikube  Started container nginx
```

## ReplicaSet

## Deployment

## Service

## Kubernetes API

## Controllers

## Operators

## License

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img
alt="Creative Commons License" style="border-width:0"
src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />This
document is licensed under a <a rel="license"
href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons
Attribution-ShareAlike 4.0 International License</a>.
