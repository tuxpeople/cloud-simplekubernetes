# cloud-simplekubernetes

## Warning
This is more or less my personal braindump. The content of this repo should be considered als unfinished, untestet and potentially harmfull. You have been warned.

## Goal
Easy setup of a small, nonproductive Kubernetes Cluster to play with, consisting of 1 master and 2 worker nodes.

## Usage
0. Have 3 Centos 7.6.1810 hosts ready (base install is sufficent)
1. Not sure, but maybe EPEL is needed on those hosts (I've it enabled).
2. Add and enable the Google Kubernetes Repo (see https://kubernetes.io/docs/setup/independent/install-kubeadm/) on those hosts
3. Clone this repo on a host which has password free access (eg. passwordless ssh keys) to the three hosts
4. Adjust the hosts file to your need.
5. Cd into the cloned repo
6. Try your luck with "ansible-playbook -i hosts kube-dependencies.yml"

You should now have the prereqs for your kubernetes cluster. You can now either follow https://kubernetes.io/docs/setup/independent/create-cluster-kubeadm/ manually (kubeadm init and networking plugin) or you can try and fix master.yml and have it run to install your master. Worker nodes are subject to manually join.

## Result
kubectl get nodes should show three nodes in ready status.

## Todo
- Fix master.yml
- Fix task "disable SELinux" to avoid failing hard wenn the playbook is run a second time
