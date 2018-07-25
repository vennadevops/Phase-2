Reference: https://docs.docker.com/compose/wordpress/

1. Create any folder. 

      ex: mkdir my_wordpress

2. Change directory to new folder: 

      ex: cd my_wordpress
      
3. Create a yal file and add the below script. If you are getting the error with below script, copy the same content from docker-compose.yml file which is attahced.

      vi docker-compose.yml

        version: '3.3'
        services:
           db:
             image: mysql:5.7
             volumes:
               - db_data:/var/lib/mysql
             restart: always
             environment:
               MYSQL_ROOT_PASSWORD: somewordpress
               MYSQL_DATABASE: wordpress
               MYSQL_USER: wordpress
               MYSQL_PASSWORD: wordpress
           wordpress:
             depends_on:
               - db
             image: wordpress:latest
             ports:
               - "8000:80"
             restart: always
             environment:
               WORDPRESS_DB_HOST: db:3306
               WORDPRESS_DB_USER: wordpress
               WORDPRESS_DB_PASSWORD: wordpress
        volumes:
            db_data:
