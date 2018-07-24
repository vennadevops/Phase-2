Docker Compose is used to run multiple containers as a single service.


    curl -L https://github.com/docker/compose/releases/download/1.22.0/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
    chmod +x /usr/local/bin/docker-compose
    
    docker-compose version
    
Creating docker-compose: docker-compose.yml

        version: '2'
        services:
          databases:
            image: mysql
            ports:
            - "3306:3306"
            environment:
            - MYSQL_ROOT_PASSWORD=passowrd
            - MYSQL_USER=user
            - MYSQL_PASSWORD=password
            - MYSQL_DATABASE=demodb
          web:
            image: nginx


      
