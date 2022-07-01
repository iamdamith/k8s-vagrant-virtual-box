# k8s, Vagrant, Virtual box

Create a local kubernetes cluster using virtualbox. A modification of the great work [danielepolencic](https://github.com/danielepolencic) did in his [gist](https://gist.github.com/danielepolencic/ef4ddb763fd9a18bf2f1eaaa2e337544). and [LocusInnovations](https://github.com/LocusInnovations/k8s-vagrant-virtualbox) did in his modifications

Please use [install-virtualbox-6-with-vagrant-in-ubuntu-mint](https://gist.github.com/iamdamith/c853014dc8321b6355a3289a3f2ba0f6) gist if you need to install virtual box and the vagrant.


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

If you are getting this error,

The IP address configured for the host-only network is not within the
allowed ranges. Please update the address used to be within the allowed
ranges and run the command again.

  Address: 10.0.0.10
  Ranges: 192.168.56.0/21

Valid ranges can be modified in the /etc/vbox/networks.conf file. For
more information including valid format see:

  https://www.virtualbox.org/manual/ch06.html#network_hostonly
  

Please create /etc/vbox/networks.conf and add 

```bash
* 10.0.0.0/8 192.168.0.0/16 172.16.0.0/12
```
