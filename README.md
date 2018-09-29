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
* Status should be similar to below
