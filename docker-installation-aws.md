# React + Vite + AWS

In this project we are crating CICD pipline on AWS EC2 instance using
> Jenkins
> Docker
> AWS - EC2 instance

Following are steps

1. Create New react project and upload it on github
2. Create a new EC2 instance on AWS (storage 24gb and RAM 2gb)
3. Install Jenkins on EC2 instance (Follow steps provided in https://github.com/98aj/Jenkins-notes)
4. Install Docker on EC2 instance
 Following are steps to install docker on EC2 instance

 1. SSH into your EC2 instance and update all packages
 
 2. Add Docker GPG key
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
 
 3. Add Docker repository
    echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | \
    
    sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
 
 4. Install Docker
    
    sudo apt update
    sudo apt install docker-ce docker-ce-cli containerd.io -y
 
 5. Add your user to the docker group

    sudo usermod -aG docker ubuntu
    newgrp docker (To refresh groups)
    and try command => docker ps

 6. Start Docker
    
    sudo systemctl start docker
    sudo systemctl enable docker

 7. Test Docker:
    docker --version
    docker run hello-world

