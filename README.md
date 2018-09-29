# cloudera-quickstart-docker-compose
Setting up a single node Cloudera Hadoop on cloud with quickstart image, docker and docker compose


### Getting Things Ready
First, it is necessary to have Docker and Docker compose running on your OS.

#### Installing Docker
* Update yum repositories  
``` sudo yum check-update ```
* Get and execute installation script of Docker  
``` curl -fsSL https://get.docker.com/ | sh ``` 
* Start Docker, verify its status and make it available upon boot  
``` sudo systemctl start docker ```  
``` sudo systemctl status docker ```  
``` sudo systemctl enable docker ```  
* An optional step: If you would like to run "docker" command without sudo, do the following (replace username with yours)  
``` sudo usermod -aG docker username ``` 
* Status should be similar to below  
![alt text](https://github.com/emirkorkmaz/cloudera-quickstart-docker-compose/blob/master/misc/images/docker_status.png "Docker Status")  

#### Installing Docker Compose
* Get epel repositories and install PIP  
``` sudo yum install epel-release ```  
``` sudo yum install -y python-pip ```  
* Install Docker Compose with PIP  
``` sudo pip install docker-compose ```  
* Update python and PIP  
``` sudo yum upgrade python* ```  
``` sudo pip install --upgrade pip ```   

