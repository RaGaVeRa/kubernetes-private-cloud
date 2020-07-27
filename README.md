# Setting up our own Kubernetes/Containers based Private Cloud 

# Tutorials
* [How to Install and Deploy Kubernetes on Ubuntu 16.04](https://dzone.com/articles/how-to-install-and-deploy-kubernetes-on-ubuntu-160-1)
* [How To Create a Kubernetes Cluster Using Kubeadm on Ubuntu 16.04](https://www.digitalocean.com/community/tutorials/how-to-create-a-kubernetes-cluster-using-kubeadm-on-ubuntu-16-04)

# 0. Preparation
* [Change Hostname in Ubuntu 16.04 Without Restart](http://ubuntuhandbook.org/index.php/2016/06/change-hostname-ubuntu-16-04-without-restart/)
* [Set up key-based authentication in SSH](https://www.digitalocean.com/community/tutorials/ssh-essentials-working-with-ssh-servers-clients-and-keys#generating-and-working-with-ssh-keys)
* [Enable `sudo` without password in Ubuntu/Debian](https://phpraxis.wordpress.com/2016/09/27/enable-sudo-without-password-in-ubuntudebian/)
* [Install Ansible - an open-source software provisioning, configuration management, and application-deployment tool enabling infrastructure as code](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)
  - [Configuration Management 101: Writing Ansible Playbooks](https://www.digitalocean.com/community/tutorials/configuration-management-101-writing-ansible-playbooks)
  - [Getting Started With Kubernetes Operators (Ansible Based)](https://medium.com/velotio-perspectives/getting-started-with-kubernetes-operators-ansible-based-part-2-472eb0d453b7)

# 1. Install Containerd
Containerd replaces docker-ce as the container runtime in Kubernetes
- [IBM Cloud Kubernetes Service Supports containerd](https://www.ibm.com/cloud/blog/ibm-cloud-kubernetes-service-supports-containerd)
- [Kubernetes Containerd Integration Goes GA](https://kubernetes.io/blog/2018/05/24/kubernetes-containerd-integration-goes-ga/)

Steps
* [Install containerd as CRI runtime](https://kubernetes.io/docs/setup/production-environment/container-runtimes/#containerd)
* [Change default cgroup driver to systemd](https://kubernetes.io/docs/setup/production-environment/container-runtimes/#cgroup-driver)
  - [Set `plugins.cri.systemd_cgroup = true` in `/etc/containerd/config.toml`](https://kubernetes.io/docs/setup/production-environment/container-runtimes/#systemd)
  - [Manually configure the cgroup driver used by kubelet](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/install-kubeadm/#configure-cgroup-driver-used-by-kubelet-on-control-plane-node)

# 2. Setup Kubernetes using kubeadm
* [Install kubeadm, kubelet and kubectl](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/install-kubeadm/)
* [Create a single control-plane cluster with kubeadm](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/create-cluster-kubeadm/)

# 3. Enable Dashboard
* [Deploy Kubernetes Dashboard](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/)
https://github.com/kubernetes/dashboard
* [Container Resource Monitoring](https://kubernetes.io/docs/tasks/debug-application-cluster/resource-usage-monitoring/)
  - [Metrics Server](https://github.com/kubernetes-sigs/metrics-server)
  - [Prometheus - Overview, Components, Architecture](https://prometheus.io/docs/introduction/overview/)
  - [Premetheus Instrumentation](https://prometheus.io/docs/introduction/faq/#instrumentation)
    - [Monitor machines using Prometheus Node exporter](https://github.com/prometheus/node_exporter)
    - [Monitor network devices using Prometheus SNMP exporter](https://github.com/prometheus/snmp_exporter)
    - [Monitor JVM applications via JMX using Prometheus JMX Exporter](https://github.com/prometheus/jmx_exporter)
    - [Monitoring Docker container metrics using cAdvisor](https://prometheus.io/docs/guides/cadvisor/)
  - [Prometheus and Grafana installation using Kustomize](https://kubernetes.github.io/ingress-nginx/user-guide/monitoring/)
  - [Kubernetes native deployment and management of Prometheus using Prometheus Operator](https://github.com/coreos/prometheus-operator)
  - [Running Prometheus on Kubernetes](https://linuxacademy.com/blog/kubernetes/running-prometheus-on-kubernetes/)

# 4. Distributed storage solution for block storage, object storage, and shared filesystems
* [Distributed File System using Ceph](https://ceph.io/ceph-storage/)
* [Ceph Tech Talk - Intro to Ceph](https://www.youtube.com/watch?v=PmLPbrf-x9g) - Slides [here](https://www.slideshare.net/Inktank_Ceph/20190627-intro-to-ceph)
* [Run Ceph in Kubernetes using Rook](https://rook.io/)
  - [Introduction to Rook: KubeCon + CloudNativeCon Seattle 2018](https://www.youtube.com/watch?v=pwVsFHy2EdE) - Slides [here](https://static.sched.com/hosted_files/kccna18/9f/Rook%20Project%20Intro%20Kubecon%20Seattle%202018.pdf)
  - [Deep Dive: Rook + Ceph: KubeCon + CloudNativeCon Seattle 2018](https://www.youtube.com/watch?v=Mb7oiXQb1ZE) - Slides [here](https://static.sched.com/hosted_files/kccna18/b6/Rook%20Deep%20Dive.pdf)
  - [Rook-Ceph Deep Drive: KubeCon + CloudNativeCon San Diego 2019](https://www.youtube.com/watch?v=f3Wyk968VR8). From 22:46 to 43:00. Slides [here](https://static.sched.com/hosted_files/kccncna19/37/KubeCon%20San%20Diego_%20Ceph%20Deep%20Dive.pdf).
* [Ceph Storage Prerequisites](https://github.com/rook/rook/blob/master/Documentation/ceph-quickstart.md#prerequisites)
  - [Use A File As A Linux Block Device](https://www.jamescoyle.net/how-to/2096-use-a-file-as-a-linux-block-device#:~:text=Just%20like%20when%20creating%20a,around%20like%20a%20normal%20file)

# 5. Useful Helm charts
[Cloud Native Computing Foundation (CNCF) Survey 2019 Report](https://www.cncf.io/wp-content/uploads/2020/03/CNCF_Survey_Report.pdf)

* https://hub.helm.sh/charts/bitnami/nginx
* https://hub.helm.sh/charts/nginx/nginx-ingress
* https://hub.helm.sh/charts/cloudposse/nfs-provisioner
* https://hub.helm.sh/charts/ibm-charts/ibm-rook-rbd-cluster
* https://hub.helm.sh/charts/stable/jenkins
* https://github.com/IBM/charts/tree/master/stable/ibm-istio
* https://gitlab.com/gitlab-org/charts/gitlab

# Other Useful References
* [Using Variables in Ansible such as `{{ansible_distribution_release}}`](https://docs.ansible.com/ansible/latest/user_guide/playbooks_variables.html)
* [Use SSH Keys With PuTTY On Windows](https://devops.ionos.com/tutorials/use-ssh-keys-with-putty-on-windows/)
* [Ansible Modules Documentation](https://docs.ansible.com/ansible/latest/modules/replace_module.html)
* [Difference between systemctl and service commands](https://askubuntu.com/questions/903354/difference-between-systemctl-and-service-commands)
* [How to check if port is in use on Linux or Unix](https://www.cyberciti.biz/faq/unix-linux-check-if-port-is-in-use-command/)
* [Private Address Space reserved by Internet Assigned Numbers Authority (IANA)](https://tools.ietf.org/html/rfc1918)
* [What is the difference between Docker, LXD, and LXC](https://unix.stackexchange.com/questions/254956/what-is-the-difference-between-docker-lxd-and-lxc)
* [How to Install and Configure VNC on Ubuntu 16.04](https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-vnc-on-ubuntu-16-04)

# Troubleshooting

* [CoreDNS pods have `CrashLoopBackOff` or `Error` state](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/troubleshooting-kubeadm/#coredns-pods-have-crashloopbackoff-or-error-state)
  - [Troubleshooting Loops In Kubernetes Clusters](https://github.com/coredns/coredns/tree/master/plugin/loop#troubleshooting)
  - [Ubuntu 16.04 Server Guide - Networking Configuration](https://help.ubuntu.com/16.04/serverguide/network-configuration.html)
  - [resolvconf — a framework for managing multiple DNS configurations](http://manpages.ubuntu.com/manpages/focal/en/man8/resolvconf.8.html)
  - [dnsmasq - A lightweight DHCP and caching DNS server](http://manpages.ubuntu.com/manpages/xenial/en/man8/dnsmasq.8.html)
  - [nameserver 127.0.1.1 in resolv.conf won't go away!](https://askubuntu.com/a/627900/419160)
  - Other related references
    * [IP Addresses, Subnet Masks, and Default Gateways](https://www.networkcomputing.com/network-security/ip-addresses-subnet-masks-and-default-gateways)
    * [NAT Configuration Primer](https://www.networkcomputing.com/networking/nat-configuration-primer)
    * [Kubernetes CoreDNS in CrashLoopBackOff](https://stackoverflow.com/questions/53559291/kubernetes-coredns-in-crashloopbackoff)
    * [Disabling DNSMASQ via Network Manager on Ubuntu 16.04+](http://www.vassox.com/linux-general/ubuntu/disabling-dnsmasq-via-network-manager-on-ubuntu-16-04/)
    * [Disabling DNSMASQ as your local DNS server in Ubuntu](https://mark.orbum.net/2012/05/14/disabling-dnsmasq-as-your-local-dns-server-in-ubuntu/)
    * [How do I set my DNS when resolv.conf is being overwritten?](https://unix.stackexchange.com/questions/128220/how-do-i-set-my-dns-when-resolv-conf-is-being-overwritten/163506#163506)
* [How to apt-delete-repository?](https://unix.stackexchange.com/questions/219341/how-to-apt-delete-repository)
* [Tear down / clean up Kubernetes cluster](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/create-cluster-kubeadm/#tear-down)
* [Use `crictl` to manually list, stop, remove pods](https://kubernetes.io/docs/tasks/debug-application-cluster/crictl/)
  - List pods `$ sudo crictl -r /var/run/containerd/containerd.sock pods`
  - Stop one or more running pods `$ sudo crictl -r /var/run/containerd/containerd.sock stopp <pod-id>`
  - Remove one or more pods `$ sudo crictl -r /var/run/containerd/containerd.sock rmp <pod-id>`
* [sudo apt-get update failing - “could not open” list file due to “permission denied”](https://askubuntu.com/questions/917603/sudo-apt-get-update-failing-could-not-open-list-file-due-to-permission-deni)
