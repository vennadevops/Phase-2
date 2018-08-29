
* Launch an Ubuntu machine with instance type t2.medium or higher than this. (I tired on t2.xlarge)

* Connect to the instance.

### Step-1: Install docker engine.

   [Dokcer-Installation-Ubuntu](https://github.com/DevOpsBasicSetup/Phase-2/blob/master/Docker/DockerEngine/2.1.Dokcer-Installation-Ubuntu.md)

### Step-2: Install docker-compose.

  [Dokcer-Compose-Installation-Ubuntu](https://github.com/DevOpsBasicSetup/Phase-2/blob/master/Docker/DockerCompose/Installation-and-example-1.md)

### Step-3: DevOps Setup using docker compose files:

##### 3.1. Install Git : apt-get install git

* Clone the repo: git clone https://github.com/DevOpsBasicSetup/Phase-2.git

##### 3.2. Run docker compose:

    change directory to Phase-2/Docker/DockerCompose/DevOps-Platfrom-Setup/

    cd Phase-2/Docker/DockerCompose/DevOps-Platfrom-Setup/

    docker-compose -f  docker-compose-apache.yml -f docker-compose-SeleniumGrid.yml -f docker-compose-jenkins-nexus.yml -f docker-compose-sonar.yml up -d
    
##### 3.3. Deploy web files:

* connect to apache webserver container: 

      docker ps
      
      docker exec -it <container-id-of-apache-web-server> bash

* Apache web files default location: /usr/local/apache2/htdocs/index.html

* Install Git & vim: apt-get update && apt-get install git vim.

* Deploy our web files to the webserver location /usr/local/apache2/htdocs/

* cp Phase-2/Docker/DockerCompose/DevOps-Platfrom-Setup/*.jpg /usr/local/apache2/htdocs/

* cp Phase-2/Docker/DockerCompose/DevOps-Platfrom-Setup/*.html /usr/local/apache2/htdocs/

![image](https://user-images.githubusercontent.com/24622526/44790055-c940b680-ab8d-11e8-8b66-993da66dc990.png)

* update index.html file with IP address: vi /usr/local/apache2/htdocs/index.html

* Launch the apache webserver URL in any browser: http://[publicIpAddress]:8080

![image](https://user-images.githubusercontent.com/24622526/44790187-35231f00-ab8e-11e8-9336-8afc2473a241.png)
