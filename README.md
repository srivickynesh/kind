# kind-cluster

### Prerequisites

1. This tool requires you to have [Docker](https://docs.docker.com/get-docker/) installed.

2. The Kubernetes command-line tool, [kubectl](https://kubernetes.io/docs/tasks/tools/) installed.

### Install kind using binary:

1. `curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.11.0/kind-linux-amd64`

2. `chmod +x ./kind`

3. `sudo mv ./kind /usr/bin/`

### Creating a single node kind-cluster:

  `kind cluster create`, creates a default cluster name as kind.

  ![Screenshot from 2021-06-25 16-14-55](https://user-images.githubusercontent.com/32717488/123413893-e95c8280-d5d0-11eb-9353-f28f0aa12465.png)


### Creating multiple clusters using kind:

`kind cluster create --name=mycluster1`

`kind cluster create --name mycluster2`

Use `k config get-contexts` to see the list of clusters created

![Screenshot from 2021-06-25 16-12-18](https://user-images.githubusercontent.com/32717488/123413986-f8dbcb80-d5d0-11eb-8e75-664ef7171ebe.png)

###### [Note]: To switch to different cluster use, `k config use-context <cluster-name>` cmd.

### Creating a multinode kind-cluster:

To setup a multinode kind-cluster environment use the yaml created from configs/control-plane-ha.yaml.

`kind create cluster --config control-plane-ha.yaml`



By default, the cluster access configuration is stored in `${HOME}/.kube/config` if $KUBECONFIG environment variable is not set. You can set the KUBECONFIG environment with `export KUBECONFIG=${HOME}/.kube/config`



### Other Useful Links:

[Advanced Installation](https://pkg.go.dev/sigs.k8s.io/kind)

[Automation Deployment tools](https://spr.com/4-tools-to-automate-kubernetes-cluster-deployments/)

[Docker permission Denied](https://www.digitalocean.com/community/questions/how-to-fix-docker-got-permission-denied-while-trying-to-connect-to-the-docker-daemon-socket)

