
## Kubernetes installation in ubuntu 22 Using Kubeadm
 - Install using the Apt repository
   Before you install Docker Engine for the first time on a new host machine, you need to set up the Docker repository. Afterward, you can install and update Docker from the repository.

 - Set up Docker's Apt repository.

Step:1 Update the apt package index and install packages needed to use the Kubernetes apt repository:

    sudo apt-get update
    sudo apt-get install -y apt-transport-https ca-certificates curl

Step:2 Download the Google Cloud public signing key:
    
    sudo curl -fsSLo /usr/share/keyrings/kubernetes-archive-keyring.gpg https://packages.cloud.google.com/apt/doc/apt-key.gpg

Step:3 Add the Kubernetes apt repository:
    
    echo "deb [signed-by=/usr/share/keyrings/kubernetes-archive-keyring.gpg] https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee /etc/apt/sources.list.d/kubernetes.list

Step:4 Update apt package index, install kubelet, kubeadm and kubectl, and pin their version:
 
    sudo apt-get update
    sudo apt-get install -y kubelet kubeadm kubectl
    sudo apt-mark hold kubelet kubeadm kubectl

Step:5 Check version 

    kubectl version --short

If you want all the things in a script [clickHere]()

Note: for more details refer  [https://kubernetes.io/docs/setup/independent/install-kubeadm/](https://kubernetes.io/docs/setup/independent/install-kubeadm/)
