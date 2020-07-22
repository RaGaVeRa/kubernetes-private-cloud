# kubernetes-private-cloud
Setting up our own Kubernetes/Containers Private Cloud 

# References
* https://dzone.com/articles/how-to-install-and-deploy-kubernetes-on-ubuntu-160-1
* https://www.digitalocean.com/community/tutorials/how-to-create-a-kubernetes-cluster-using-kubeadm-on-ubuntu-18-04

# Preparation
0) http://ubuntuhandbook.org/index.php/2016/06/change-hostname-ubuntu-16-04-without-restart/
1) https://www.digitalocean.com/community/tutorials/ssh-essentials-working-with-ssh-servers-clients-and-keys#generating-and-working-with-ssh-keys
2) https://phpraxis.wordpress.com/2016/09/27/enable-sudo-without-password-in-ubuntudebian/
3) https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html

# Install Containerd
* https://kubernetes.io/docs/setup/production-environment/container-runtimes/#containerd
* Change default cgroup driver to systemd https://github.com/kubernetes/kubeadm/issues/1394#issuecomment-462878219

## Other useful references
* https://docs.ansible.com/ansible/latest/user_guide/playbooks_variables.html
* https://unix.stackexchange.com/questions/219341/how-to-apt-delete-repository
* Kubernetes container runtime containerd replaces Docker
  - https://www.ibm.com/cloud/blog/ibm-cloud-kubernetes-service-supports-containerd
  - https://kubernetes.io/blog/2018/05/24/kubernetes-containerd-integration-goes-ga/
