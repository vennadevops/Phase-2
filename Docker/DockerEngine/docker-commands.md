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

     docker container ls

#### Example-2:

    docker create --publish 8081:80 --name apache-web httpd

    docker ps -a Or docker container ls --all

    docker exec -it apache-web "/bin/bash"

        apt-get update -y

        apt-get install vim -y

        vi /usr/local/apache2/htdocs/index.html

     echo "<h1>Hello Friends... welcome to Docker..</h1>" > index.html

     ls

     docker cp index.html apache-web:/usr/local/apache2/htdocs/index.html
   
     docker container stop webserver apache-web
     
     docker container rm webserver apache-web
  
        
  
