# Go Application Development with Kubernetes

Welcome to Application Development with Kubernetes tutorial!  You can develop an
application without using Kubernetes.  However, if you target to deploy the
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
