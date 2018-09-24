#### Example-1:

  docker run --detach --publish 80:80 --name webserver nginx
  
  docker exec -it webserver "/bin/bash"
  
      apt-get update -y

      apt-get install vim -y

      vi /usr/share/nginx/html/index.html
    
   docker exec -it webserver echo "hello devops"
   
   docker exec -it webserver mkdir "devops"
   
   docker exec -it webserver echo "hello devops"
   
   docker exec -it webserver touch "devops.txt"
   
   
  
  

  
