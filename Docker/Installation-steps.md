
## Docker installation in ubuntu 22
 - Install using the Apt repository
   Before you install Docker Engine for the first time on a new host machine, you need to set up the Docker repository. Afterward, you can install and update Docker from the repository.

 - Set up Docker's Apt repository.

Step:1 Add Docker's official GPG key:
     
    sudo apt-get update
    sudo apt-get install ca-certificates curl gnupg
    sudo install -m 0755 -d /etc/apt/keyrings
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
    sudo chmod a+r /etc/apt/keyrings/docker.gpg

Step:2 Add the repository to Apt sources:
    
    echo \
      "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
      "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
      sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
    sudo apt-get update

Step:3 To install latest version 
    
    sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
 
   Test the Docker using version or sample applicaiton deployment

    docekr --version
    sudo docker run hello-world

   Post Insatllion steps - To create the docker group and add your user for non **sudo** user

     sudo groupadd docker
     sudo usermod -aG docker $USER

If you want all the things in a script [clickHere](https://github.com/Simha06N/DevOps_Cheatsheet/blob/main/Docker/docker-instalation.sh)

Note: for more details refer  [https://docs.docker.com/install/linux/docker-ce/ubuntu/#install-docker-ce-1](https://docs.docker.com/install/linux/docker-ce/ubuntu/#install-docker-ce-1)
