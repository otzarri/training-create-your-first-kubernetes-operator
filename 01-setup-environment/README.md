# Setup environment

Before beginning this tutorial it is necessary that you have installed the tools that will be used.

**In this challenge you will:**

* Install the required tools
* Create a local kubernetes cluster

## 🐋 Install Docker

Docker is a tool that is used to automate the deployment of applications in lightweight containers so that applications can work efficiently in different environments. `Kind` will create here the nodes for the Kubernetes clusters.

Follow the [Docker installation instructions](https://docs.docker.com/engine/install/) for your OS and install it.

## 🐿️ Install the Go language

Go is a general-purpose programming language, so you can write any operator logic you want. Kubernetes itself is written in Go, so this language interacts smoothly with Kubernetes API.

You can chose between installing Go using the package manager of your operating system or using [gvm](https://github.com/moovweb/gvm), which enables your system to keep different versions of Go installed and switch between them on-demand.

Install `gvm` with the command below. If you are using bash just change `zsh` with `bash`.

```
zsh < <(curl -s -S -L https://raw.githubusercontent.com/moovweb/gvm/master/binscripts/gvm-installer)
source ~/.gvm/scripts/gvm
```

Install go version 1.19 and set it as default version:

```shell
gvm install go1.19
gvm use go1.19 --default
```

## 📦 Install arkade

Arkade defines itself as the open source marketplace for Kubernetes and the way developers install the latest versions of their favourite tools and Kubernetes apps. With arkade get, you'll have kubectl, kind, terraform, and jq on your machine faster than you can type apt-get install/brew update. With over 100 CLIs and 55 Kubernetes apps (charts, manifests, installers) available for Kubernetes, gone are the days of contending with dozens of README files just to set up a development stack with the usual suspects like ingress-nginx, Postgres and cert-manager.

You will use arkade to install some dependencies in this tutorial. Install it running the command below:

```
curl -sLS https://get.arkade.dev | sudo sh
```

Add arkade binary directory to your PATH variable:

```
echo '
# Arkade support
[ -d "$HOME/.arkade/bin" ] && PATH="$HOME/.arkade/bin:$PATH"
' > $HOME/.zshrc
```

## 🖵  Install kubectl

Kubernetes provides a command line tool for communicating with a Kubernetes cluster's control plane, using the Kubernetes API. This tool is named `kubectl`. For configuration, `kubectl` looks for a file named config in the $HOME/.kube directory. You can specify other kubeconfig files by setting the `KUBECONFIG` environment variable or by setting the `--kubeconfig` flag.

To install `kubectl`:

```
arkade get kubectl
```

## 🏗️ Install kubebuilder

Kubebuilder is an SDK for rapidly building and publishing Kubernetes APIs in Go. It builds on top of the canonical techniques used to build the core Kubernetes APIs to provide simple abstractions that reduce boilerplate and toil. Similar to web development frameworks such as Ruby on Rails and SpringBoot, Kubebuilder increases velocity and reduces the complexity managed by developers.

To install `kubebuilder`:

```
arkade get kubebuilder
```

## 🍶 Install kind

[kind](https://kind.sigs.k8s.io/) is a tool for running local Kubernetes clusters using Docker container "nodes", bootstraping each “node” with [kubeadm](https://kubernetes.io/docs/reference/setup-tools/kubeadm/). It was primarily designed for testing Kubernetes itself, but may be used for local development or CI. It's lightweight and easy to integrate in the development workflows.

Run the command below to install `kind`.

```
arkade get kind
```

## ⎈ Create a single-node local Kubernetes cluster

You need a running Kubernetes cluster to develop the operator. Let's deploy a single-node cluster locally for a faster development.

Use this command to create the cluster:

```
kind create cluster
```

Configure `kubectl` to use this cluster:

```
kubectl cluster-info --context kind-kind
```

Check you can operate the cluster with `kubectl`:

```
kubectl get all -A
```

Additionally, you can see the Docker container running the kubernetes node. The container name is `kind-control-plane`.

```
docker ps 
```

## ⚙️ System configuration

This is the configuration of the system used to build this tutorial:

| Setting      | Value                  |
| ------------ | ---------------------- |
| Architecture | x86_64                 |
| OS family    | GNU/Linux              |
| OS distro    | Manjaro 22.0.3 Sikaris |
| K8s distro   | kind 0.17.0            |
| Go version   | 1.19                   |
| kubebuilder  | 3.9.0                  |
| kubectl      | 1.25.3                 |

<hr>
<a href="../../../">⬅️</a>
<a href="../02-generate-application-scaffolding/">➡️</a>
