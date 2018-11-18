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
``` sudo pip install docker-compose --ignore-installed ``` (in case you're running pip 10)  
* Update python and PIP  
``` sudo yum upgrade python* ```  
``` sudo pip install --upgrade pip ```  

#### Setting up Single Node Cloudera Hadoop with Docker Compose  
* Get the docker-compose.yaml file from https://github.com/emirkorkmaz/cloudera-quickstart-docker-compose/blob/master/cloudera-quickstart/docker-compose.yaml and store it in a proper folder  
* Change directory to the folder where docker-compose.yaml exists  
* Execute following command and wait for docker and docker compose do the things for you (If you dont want to see the trace simply execute the command on detach mode)  
``` docker-compose up ``` 
* In the end, you see following final lines that means your Single Node Cloudera Hadoop is ready to use  
![alt text](https://github.com/emirkorkmaz/cloudera-quickstart-docker-compose/blob/master/misc/images/installation_done.png "Installation Done!")  
* Try to each and use Hue, http://IP:8888. User name and password is cloudera/cloudera  
![alt text](https://github.com/emirkorkmaz/cloudera-quickstart-docker-compose/blob/master/misc/images/hue_login.png "Hue Login")  
![alt text](https://github.com/emirkorkmaz/cloudera-quickstart-docker-compose/blob/master/misc/images/hue_my_documents.png "Hue My Documents")  

#### Start up Cloudera Manager
Having installation completed, Cloudera Manager is still disabled and it is better to enable it. Here is the simple guide for enabling Cloudera Manager  

* List the quickstart container and attach to it  
``` docker ps ```   
``` docker attach container-id ```  
* Execute following command in container for enabling Cloudera Manager. It will take couple of minutes to be completed  
``` /home/cloudera/cloudera-manager --express ```  
![alt text](https://github.com/emirkorkmaz/cloudera-quickstart-docker-compose/blob/master/misc/images/cm_installed.png "CM Installed")  
* When CM is being started, it stops all services. Hence it is necessary to restart them all over Cloudera Manager
![alt text](https://github.com/emirkorkmaz/cloudera-quickstart-docker-compose/blob/master/misc/images/cm_start.png "CM Installed")  

and We're done! Single node Cloudera Hadoop is ready for use

![alt text](https://github.com/emirkorkmaz/cloudera-quickstart-docker-compose/blob/master/misc/images/cm_services_started.png "We're Done")  
