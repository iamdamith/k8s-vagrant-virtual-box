# k8s, Vagrant, Virtual box

Create a local kubernetes cluster using virtualbox. A modification of the great work [danielepolencic](https://github.com/danielepolencic) did in his [gist](https://gist.github.com/danielepolencic/ef4ddb763fd9a18bf2f1eaaa2e337544). and [gist](https://gist.github.com/danielepolencic/ef4ddb763fd9a18bf2f1eaaa2e337544) did in his modifications


The vagrant file will do the following:
1.  Provision all local VMs using VirtualBox
2.  Patch the OS
3.  Install Docker
4.  Install k8s control plane
5.  Initialize cluster with Flannel CIDR block & install Flannel
6.  Join the nodes to the master
7.  Create alias in vagrant home for kubectl...just use k



## Open a shell and clone

```bash
$ git clone https://github.com/iamdamith/k8s-vagrant-virtual-box
$ cd iamdamith/k8s-vagrant-virtual-box
```

## Starting the cluster

You can create the cluster with:

```bash
$ vagrant up
```

## Clean up

You can delete the cluster with:

```bash
$ vagrant destroy -f
```

## SSH and other Commands

SSH to Master and other Nodes:

```bash
$ vagrant ssh master
$ vagrant ssh worker1
$ vagrant ssh worker2
```
