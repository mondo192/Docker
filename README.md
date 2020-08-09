# Docker
## Quick start
* To start an interactive container ```docker container run -ti <image>```
* To access already running container through bash ```docker container exec -ti alpine sh``` 

## Cleanup 
* To remove all downloaded images, combine two comands. First to list all image ID's and then remove.```docker image rmi $(docker image ls -a -q)```
* To stop all containers and remove them. ```docker container rm -f $(docker container ls -a -q)```
  
