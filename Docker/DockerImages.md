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
    

