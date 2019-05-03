# docker usuful things

## Description

Useful commands that I use every day

## Configuration

-Docker Server Settings -> [How to enable the remote API for docker](https://success.docker.com/article/how-do-i-enable-the-remote-api-for-dockerd)
>client = docker.DockerClient(base_url='tcp://0.0.0.0:2376')


## Docker Commands
 
##### Show information
>sudo docker ps --size

##### Список image с указанием размера, количества и активных image
>sudo docker system df

##### Delete unused images
>sudo docker image prune -a

##### Delete unused images by CREATED date
>sudo docker image prune -a --filter "until=$(date +'%Y-%m-%dT%H:%M:%S' --date='-15 days')"

##### Delete all containers
>docker rm $(docker ps -a -q)

##### Delete all images
>docker rmi $(docker images -q)

##### Stop all images (better use kill)
>docker kill $(docker ps -a -q)
>sudo docker kill $( sudo docker ps -a -q)
>docker stop $(docker ps -a -q)

##### Restart all containers
>docker restart $(docker ps -a -q)

##### Delete all stopped images
>sudo docker rm $(sudo docker ps -q -f status=exited)

##### Delete all dangling (unused) images
>sudo docker rmi $(sudo docker images -q -f dangling=true)

##### Delete all dangling (unused) volumes -> volumes remains after deleting containers and images
>sudo docker volume rm $( sudo docker volume ls -q) 

##### Stop(kill) all containers with name <container_name>
>sudo docker kill $( sudo docker ps -aqf "name=<container_name>")

##### Узнать  подключился ли процесс к определенному порту/сокету
>sudo lsof -i : *port*

##### Show container information in JSON:
>docker inspect container_name


## Docker Image Controls

##### Save image
>docker save -o *path_for_generated_tar_file* *image_name*

##### Load image
>docker load -i *path_to_image_tar_file*

## Links

[Standard copy tools](https://www.shellhacks.com/ru/copy-files-ssh-10-examples/)

## License

Free