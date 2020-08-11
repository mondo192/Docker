# Docker
## Quick start
* Build image ```docker build --no-cache --build-arg TOKEN="<personal-access-token>" -t go-alpine .``` 
* Access container ```docker container run --rm -it go-alpine```

## Cleanup 
* To remove all downloaded images, combine two comands. First to list all image ID's and then remove.```docker image rmi $(docker image ls -a -q)```
* To stop all containers and remove them. ```docker container rm -f $(docker container ls -a -q)```

# Jenkins
## Quick start
Run the container with a mounted volume
```docker run -d -p 8080:8080 -v jenkins_home:/var/jenkins_home --name jenkins jenkins/jenkins:lts```
Output the initial admin password
```docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword```

