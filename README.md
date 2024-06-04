# Jenkins-Docker-Learning
Learning Jenkins and Docker

# How to initialise Jenkins using Docker

To initialise Jenkins using Docker you need to download the Docker desktop first: https://docs.docker.com/get-docker/

## Check the Docker version

`docker --version`
## Pull the latest jenkins version
`docker pull jenkins/jenkins:lts`

## Create and run a container named jenkins on port:8080
`docker run --detach --publish 8080:8080 --volume jenkins_home:/var/jenkins_home --name jenkins jenkins/jenkins:lts`

## Retrieve the initial admin password
`docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword`


# How to restart the procedure and register again with new admin password:

## Stop and remove
```
docker stop jenkins
docker rm jenkins
```

## Remove the Existing Volume:
This is important to remove the old configuration data that's causing the setup wizard to persist.

`docker volume rm jenkins_home`

## Recreate the Container with the Setup Wizard Disabled:
`docker run --detach --publish 8080:8080 --volume jenkins_home:/var/jenkins_home --name jenkins jenkins/jenkins:lts`


## Access Jenkins:
Open your browser and go to http://localhost:8080. You should now be prompted to create a new admin user.
