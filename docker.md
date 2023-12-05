if install desktop version of docker on windows it work on wls as well

- you can use docker hub to download image for docker

```bash
      docker pull docker/whalesay # download whalesay image from docker
      # you can run it by :
      docker run docker/whalesay cowsay hello
      docker run -d  someapp # -d make this image run on background
      sudo docker run -t -d --name # first centos  you can set name for container
          # but you can bring image in console again with this command
      docker attach [id]

```
- list all containers 

 ```bash 
 docker ps # show active image 
 docker ps -a # show active and stoped 
```
- show all image   
 ```bash 
 docker images 
```

- stop docker 
 ```bash 
 docker stop [someimage] # show active image 
```
- remove instance of  stoped image  
 ```bash 
 docker rm [someimage] # show active image 
```
- remove image file 
```
sudo docker rmi some_image
```


- run commnad on docker imaege
```bash
docker exec somedocker cat etc/h
docker exec -it somedocker bash # open bash 
```






