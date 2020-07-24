# Setting up our own Kubernetes/Containers based Private Cloud 

# References
* [How to Install and Deploy Kubernetes on Ubuntu 16.04](https://dzone.com/articles/how-to-install-and-deploy-kubernetes-on-ubuntu-160-1)
* [How To Create a Kubernetes Cluster Using Kubeadm on Ubuntu 16.04](https://www.digitalocean.com/community/tutorials/how-to-create-a-kubernetes-cluster-using-kubeadm-on-ubuntu-16-04)
* [Cloud Native Computing Foundation (CNCF) Survey 2019 Report](https://www.cncf.io/wp-content/uploads/2020/03/CNCF_Survey_Report.pdf)

# Preparation
0) [Change Hostname in Ubuntu 16.04 Without Restart](http://ubuntuhandbook.org/index.php/2016/06/change-hostname-ubuntu-16-04-without-restart/)
1) [Setting up key-based authentication in SSH](https://www.digitalocean.com/community/tutorials/ssh-essentials-working-with-ssh-servers-clients-and-keys#generating-and-working-with-ssh-keys)
2) [Enable `sudo` without password in Ubuntu/Debian](https://phpraxis.wordpress.com/2016/09/27/enable-sudo-without-password-in-ubuntudebian/)
3) [Install Ansible - an open-source software provisioning, configuration management, and application-deployment tool enabling infrastructure as code](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)

# Install Containerd
* Containerd replaces docker-ce as the container runtime in Kubernetes
  - [IBM Cloud Kubernetes Service Supports containerd](https://www.ibm.com/cloud/blog/ibm-cloud-kubernetes-service-supports-containerd)
  - [Kubernetes Containerd Integration Goes GA](https://kubernetes.io/blog/2018/05/24/kubernetes-containerd-integration-goes-ga/)
* [Steps to use containerd as CRI runtime](https://kubernetes.io/docs/setup/production-environment/container-runtimes/#containerd)
* [Change default cgroup driver to systemd](https://kubernetes.io/docs/setup/production-environment/container-runtimes/#cgroup-driver)
  - [Set `plugins.cri.systemd_cgroup = true` in `/etc/containerd/config.toml`](https://kubernetes.io/docs/setup/production-environment/container-runtimes/#systemd)
  - [Manually configure the cgroup driver used by kubelet](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/install-kubeadm/#configure-cgroup-driver-used-by-kubelet-on-control-plane-node)

## Other useful references
* [Using Variables in Ansible such as `{{ansible_distribution_release}}`](https://docs.ansible.com/ansible/latest/user_guide/playbooks_variables.html)
* [Use SSH Keys With PuTTY On Windows](https://devops.ionos.com/tutorials/use-ssh-keys-with-putty-on-windows/)

# Troubleshooting

* [CoreDNS pods have `CrashLoopBackOff` or `Error` state](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/troubleshooting-kubeadm/#coredns-pods-have-crashloopbackoff-or-error-state)
  - [Troubleshooting Loops In Kubernetes Clusters](https://github.com/coredns/coredns/tree/master/plugin/loop#troubleshooting)
  - [Ubuntu 16.04 Server Guide - Networking Configuration](https://help.ubuntu.com/16.04/serverguide/network-configuration.html)
  - [resolvconf — a framework for managing multiple DNS configurations](http://manpages.ubuntu.com/manpages/focal/en/man8/resolvconf.8.html)
  - [dnsmasq - A lightweight DHCP and caching DNS server](http://manpages.ubuntu.com/manpages/xenial/en/man8/dnsmasq.8.html)
  - [nameserver 127.0.1.1 in resolv.conf won't go away!](https://askubuntu.com/a/627900/419160)

* [How to apt-delete-repository?](https://unix.stackexchange.com/questions/219341/how-to-apt-delete-repository)
