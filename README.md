# Jenkins-Docker-Learning
Learning Jenkins and Docker

To initialise Jenkins using Docker you need to download the Docker desktop first: https://docs.docker.com/get-docker/

#Check the Docker version
`docker --version`
# Pull the latest jenkins version
`docker pull jenkins/jenkins:lts`

# Create and run a container named jenkins on port:8080
`docker run --detach --publish 8080:8080 --volume jenkins_home:/var/jenkins_home --name jenkins jenkins/jenkins:lts`

# Retrieve the initial admin password
`docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword`
