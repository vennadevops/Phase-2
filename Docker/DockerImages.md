###### Interact with container: sudo docker exec -it [containerId] bash

# Jenkins image

sudo docker pull jenkins

sudo docker inspect jenkins

sudo docker run -p 8080:8080 -p 50000:50000 jenkins

Launch the URL in any brwoser: http:publicIP:8080

# Nexus image

    sudo docker pull sonatype/nexus

    sudo docker inspect sonatype/nexus
  
    docker run -d -p 8081:8081 --name nexus sonatype/nexus:latest

    Launch the URL: http:publicIP:8081/nexus
    
# Nginx image

    sudo docker pull nginx
    
    sudo docker inspect nginx
    
    sudo docker run --publish 8082:80 nginx
    
    Launch the URL in any brwoser: http:publicIP:8082
    
    Webpages location: /usr/share/nginx/html
    
# SonarQube image: https://hub.docker.com/_/sonarqube/

    sudo docker run -d --name sonarqube -p 9000:9000 -p 9092:9092 sonarqube
    
    Launch the URL in any brwoser: http:publicIP:9000

# Selenium Grid (hub & node): https://github.com/SeleniumHQ/docker-selenium

    docker network create grid
    
    docker run -d -p 4444:4444 --net grid --name selenium-hub selenium/hub:3.13.0-argon
    
    docker run -d --net grid -e HUB_HOST=selenium-hub -v /dev/shm:/dev/shm selenium/node-chrome:3.13.0-argon
    
    docker run -d --net grid -e HUB_HOST=selenium-hub -v /dev/shm:/dev/shm selenium/node-firefox:3.13.0-argon

    Launch the URL in any brwoser: http://18.221.217.120:4444/grid/console
