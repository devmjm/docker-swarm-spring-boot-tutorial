# Deploying Spring Boot on Docker Swarm (Mode) in Azure
The steps and resource below provide a high-level approach to deploying the Spring Boot Registry, Admin, and Config servers to Docker Swarm Mode, hosted in Azure. Note the [Common Issues and Fixes](https://github.com/devmjm/docker-swarm-spring-boot-tutorial/blob/master/README.md#common-issues-and-fixes) section below addresses potential issues you may encounter.

## Tutorial
### Part 1: Configure Azure VMs
https://docs.docker.com/docker-for-azure/#prerequisites

### Part 2: Create Azure Container Registry
* Create container registry: https://docs.microsoft.com/en-us/azure/container-registry/container-registry-get-started-portal  
* Push/Pull images from registry: https://docs.microsoft.com/en-us/azure/container-registry/container-registry-get-started-docker-cli

### Part 3: Deploy Containers to Azure
https://docs.docker.com/docker-for-azure/deploy/#worker-nodes

### Part 4: Deploy Docker Swarm using Compose file
https://medium.com/lucjuggery/deploy-the-voting-apps-stack-on-a-docker-swarm-4390fd5eee4  
<i>Note:</i> this repository includes a sample `docker-compose.yml` file for your reference.

## Common Issues and Fixes
##### Error during SSH - Could not open a connection to your authentication agent  
Fix: execute `eval $(ssh-agent)`  
Reference: https://stackoverflow.com/a/21909432  

##### Create SSH on Windows  
https://docs.docker.com/docker-cloud/cloud-swarm/ssh-key-setup/#add-your-key-to-the-ssh-agent  

##### Delete all Docker Containers
command line: `docker rm -f $(docker ps -a -q)`

##### Delete all Docker Images
command line: `docker rmi -f $(docker images -q)`
