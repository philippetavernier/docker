# docker
install and use

# INSTALL DOCKER UBUNTU
       sudo apt install apt-transport-https ca-certificates curl software-properties-common
       curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
       sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"
       sudo apt-get update
       apt-cache policy docker-ce
       sudo apt-get install docker-ce
       sudo apt-get install docker-ce-cli containerd.io
       sudo systemctl status docker
#--------------------------------

# IMAGES MANIPULATION

       #PULL MINIMAL DOCKER IMAGES      
              sudo docker pull debian

       #LIST DOCKER IMAGES      
              sudo docker images
              
       #LIST DOCKER IMAGES RUNING
              sudo docker ps
              sudo docker ps -aq
       
       #STOP DOCKER CONTAINER IMAGES RUNING
              sudo docker rm go-graphite
       
       #RUN 'debian' IMAGE
              sudo docker run -i -t debian
              
       #CONNECT to a docker container runnig in demon mode
              docker exec -it container container-name bash
              
       #CONNECT to a docker container runnig in demon mode as ROOT
              docker exec -u 0 -it mycontainer bash
       
       #SAVE 'debian' IMAGE to 'debian-voip' -> (9800d3701775) instance number when docker is exited
              sudo docker commit 9800d3701775 debian-voip
 
       #RUN 'debian-voip' IMAGE
              sudo docker run -i -t debian-voip
              sudo docker run -i -t -p 5060:5060 debian-voip


       

#--------------------------------

# NETWORK MANIPULATION

       ##LIST DOCKER NETWORK DRIVER
              sudo docker network ls
              sudo docker network inspect bridge
              sudo  docker network rm mynetwork
              sudo  docker network create --driver=macvlan --subnet=192.168.15.0/24 --gateway=192.168.15.1 -o parent=enp2s0 mynetwork
              sudo docker run -i -t -p 5060:5060 --network mynetwork --ip 192.168.15.22 debian-voip
              sudo docker run -i -t -p 5060:5060 --network mynetwork --ip 192.168.15.22 debian-voip

https://hackmd.io/@YSaVczpYQySlUnehD8yxvw/r1jk4NkBO
