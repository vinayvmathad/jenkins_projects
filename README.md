# jenkins_projects

This repository contains Jenkins pipeline scripts demonstrating how to automate various CI/CD processes. The pipelines are designed to simplify tasks like building, testing, and deploying applications. Below is a detailed overview of the content and how to use it.
## Prerequiste
* AWS EC2 instance
* Jenkins
*  Docker
### Procedure
 * Create a EC2 instance to install jenkins and docker .
 *  Install jenkins
Run the below commands to install Java and Jenkins
#### Install Java 
``` bash 
sudo apt update
sudo apt install openjdk -17-jre
```
#### Install Jenkins
``` bash 
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
```
#### Make changes for inbound traffic on Ec2
* Go to Ec2 instance and click on Security groups.
* Add inbound traffic as ALL traffic and save it.
#### Login to Jenkins using the below URL:
* http://[IPv4 address of Ec2 instance]:8080
* After setting up jenkins install docker plugins.
* Install the Docker Pipeline plugin in Jenkins:
* Log in to Jenkins.
* Go to Manage Jenkins > Manage Plugins.
* In the Available tab, search for "Docker Pipeline".
* Select the plugin and click the Install button.
* Restart Jenkins after the plugin is installed.

###### Docker Slave Configuration
* Run these commands one by one.
``` bash
sudo apt update
sudo apt install docker.io
sudo su - 
usermod -aG docker jenkins
usermod -aG docker ubuntu
systemctl restart docker
```

