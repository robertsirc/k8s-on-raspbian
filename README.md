## Kubernetes on Raspbian

This repository holds the "original tutorial" for "Kubernetes on Raspbian" by Alex Ellis using kubeadm. It also has a list of reader's clusters for your inspiration and Alex's newest work with k3s.

![My modest stack of RPis](https://miro.medium.com/max/1400/1*wDwPc6YYVbu1I8Ef9m5lBg.jpeg)

If you'd like to read more about Kubernetes clusters, see Alex's write-up over the past 5 years of building with Docker and these tiny devices:

[Five years of Raspberry Pi Clusters](https://medium.com/@alexellisuk/five-years-of-raspberry-pi-clusters-77e56e547875)

### Start the guide

Pick between `k3s` or `kubeadm`.

#### 1) Pick `k3s` (recommended)

My current recommendation is to use [k3s](https://k3s.io) from Rancher Labs. It is normal Kubernetes and passes the conformance tests written by the CNCF. I'm yet to be convinced of why someone wouldn't use this for a hobbyist build and I've been pleasantly surprised by it. Rancher Labs offers commercial support and k3s is GA, even more reason to use this option.

k3s is:

* faster, and uses fewer resources - 300MB for a server, 50MB for an "agent"
* well-maintained and ARMHF / ARM64 just works
* HA is available as of k3s 1.0 along with Kubernetes 1.16
* still normal, upstream, compliant Kubernetes
* doesn't appear to run into some of the complicated issues we've seen with `kubeadm`

![k3sup diagram](https://github.com/alexellis/k3sup/raw/master/docs/k3sup-cloud.png)

You may also enjoy k3sup ("ketchup") - a tool I built with the community to bootstrap k3s clusters over SSH. It has a simple `k3sup install / join` syntax and is available on GitHub. See more at: [https://k3sup.dev](https://k3sup.dev)

Start with a tutorial now (newest listed first):

* [Walk-through — install Kubernetes to your Raspberry Pi in 15 minutes](https://medium.com/@alexellisuk/walk-through-install-kubernetes-to-your-raspberry-pi-in-15-minutes-84a8492dc95a)
* [Kubernetes Homelab with Raspberry Pi and k3sup](https://blog.alexellis.io/raspberry-pi-homelab-with-k3sup/)
* [Will it cluster? k3s on your Raspberry Pi](https://blog.alexellis.io/test-drive-k3s-on-raspberry-pi/)

#### 2) Or pick `kubeadm` (advanced users)

This guide is part of a larger blog post: [Build your own bare-metal ARM cluster](https://blog.alexellis.io/build-your-own-bare-metal-arm-cluster/).

My current thinking is that only advanced users should attempt to install Kubernetes with `kubeadm`. Historically, it's had some unfortunate issues around timeouts and being slow, k3s makes installation and operation seamless.

* Start the guide: [Kubernetes on (vanilla) Raspbian Lite](./GUIDE.md)

Once you're up and running please share your clusters on Twitter with [@alexellisuk](https://twitter.com/alexellisuk).

You can also join the OpenFaaS Slack community's dedicated channel for ARM and Raspberry Pi #arm-and-pi. Just email alex at openfaas dot com for your invitation.

### Attribution

You're welcome to make use of this guide and to refer to it, but please do not copy it or pass it off as your own without giving attribution to the author(s). If you have suggestions or have found that some of the instructions have fallen out of date, then please see the Contributions section below on how to contribute.

#### Reader's clusters

* [Dino Fizzotti - Raspberry Pi Cluster Part 2: ToDo API running on Kubernetes with k3s](https://www.dinofizzotti.com/blog/2020-05-09-raspberry-pi-cluster-part-2-todo-api-running-on-kubernetes-with-k3s/)
* [Jim Angel's Kubernetes cluster for testing unreleased alpha / beta k8s versions](https://twitter.com/JimmAngel/status/1265087793170178048)
* [roncrivera's 4-node home-lab running OpenFaaS in a gun-case](https://twitter.com/roncrivera/status/1078552483029381121)
* [Scott Hanselman's 6-node cluster running Kubernetes, OpenFaaS with the Pimoroni blinkt!](https://twitter.com/shanselman/status/953716434458247168) [Scott's cluster-selfie](https://twitter.com/alexellisuk/status/955568790061936640)
* [Ken Fukuyama's Kubernetes cluster running OpenFaaS](https://twitter.com/kenfdev/status/954748775678976000) from Japan
* [Karol Stępniewski's Asus Tinkerboard cluster running OpenFaaS and K8s](https://twitter.com/kars7e/status/948122096969818113)
* [Bart Plasmeijer's K8s cluster](https://twitter.com/bartplasmeijer/status/933778520500731904)
* [Burton Rheutan's cluster stashed away in a closet](https://twitter.com/_burtonr/status/1033745565379641344)
* [Kevin Turcios' OpenFaaS cluster](https://twitter.com/kjturcios/status/1071253482441715713)
* [Estelle Auberix' OpenFaaS and K8s cluster for ServerlessConf Paris](https://twitter.com/chussenot/status/960849791776419840)
* [Davy's Kubernetes and OpenFaaS cluster](https://twitter.com/realDavyHua/status/1028862482259931137)
* [Jaigouk Kim's OpenFaaS and K8s cluster with the Asus Tinkerboard](https://twitter.com/jaigouk/status/964529214564298756)
* [Ram's 7-node homelab with OpenFaaS and Kubernetes](https://twitter.com/rprakashg/status/947347563912470528)
* [David Muckle's OpenFaaS cluster](https://twitter.com/dvdmuckle/status/977297461210484737)
* [Brian Moelk's battery-powered OpenFaaS cluster](https://twitter.com/brianmoelk/status/954459005149175809)
* [Marcus Smallman' DIY Raspberry Pi Kubernetes Cluster](https://marcussmallman.io/2018/02/18/diy-rasberry-pi-kubernetes-cluster/)
* [Mathias Deremer-Accettone's Serverless sur Raspberry PI avec Docker Swarm et OpenFaas](https://blog.ineat-conseil.fr/2019/01/serverless-sur-raspberry-pi-avec-docker-swarm-et-openfaas-partie-1-installation-dopenfaas/)
* [Daniel Llewellyn's three node Raspberry Pi Swarm](https://twitter.com/diddledan/status/1088759711745351682)
* [Gareth Bradley's 6 node Raspberry Pi Kubernetes Cluster](https://garfbradaz.github.io/blog/2019/02/12/RaspberryPi-Cluster-Kubernetes.html)
* [Andreas Muttscheller's Raspberry Pi OpenFaaS k3s cluster provisioned with Ansible](https://blog.codecentric.de/en/2019/08/serverless-functions-k3s-openfaas-raspberry-pi/)
* [Ruan Bekker's K3s Setup with Golang and Traefik on a Raspberry Pi 4](https://sysadmins.co.za/running-k3s-on-the-raspberrypi-4/?pk_campaign=github-teamserverless)
* [Robert Sirchia's MicroK8s with 64-bit OS on Raspberry Pi 4](https://sirchia.cloud/posts/microk8s-on-64-bit-os-raspberry-pi/)

Submit your cluster and description by creating a GitHub issue.

#### Adaptations / derived works

* ["Kubernetes on Raspbian" with Ansible](https://rak8s.io) by Chris Short
* ["Kubernetes on Raspbian" for .NET Core / Windows developers](https://www.hanselman.com/blog/HowToBuildAKubernetesClusterWithARMRaspberryPiThenRunNETCoreOnOpenFaas.aspx) by Scott Hanselman
* ["Kubernetes on Raspbian" broken-up into bash scripts with a custom laser-cut design](https://kubecloud.io/setup-a-kubernetes-1-9-0-raspberry-pi-cluster-on-raspbian-using-kubeadm-f8b3b85bc2d1) by Kasper Nissen
* ["Kubernetes on Raspbian" with Packer](https://blog.codybunch.com/2018/01/05/OpenFaaS-on-Kubernetes-on-Raspberry-Pi/) by Cody Bunch
* ["Kubernetes on Raspbian" adapted for HypriotOS](https://gist.github.com/elafargue/a822458ab1fe7849eff0a47bb512546f) by  Edouard Lafargue
* [Make your very own Kubernetes cluster from Raspberry PI](https://medium.com/nycdev/k8s-on-pi-9cc14843d43) - unattributed, copy/paste from this guide/repository


### Contributions

See: [CONTRIBUTING](CONTRIBUTING.md)