
Refer: https://docs.docker.com/compose/compose-file/

A docker-compose.yml file is organized into four sections:


| Directive | Use |
| --- | --- |
| version | Specifies the Compose file syntax version. This guide will use Version 3 throughout. |
| services | In Docker a service is the name for a “Container in production”. This section defines the containers that will be started as a part of the Docker Compose instance. |
| networks | This section is used to configure networking for your application. You can change the settings of the default network, connect to an external network, or define app-specific networks. |
| volumes | Mounts a linked path on the host machine that can be used by the container. |

directives used to set up and configure containers/services:

| Directive | Use |
| --- | --- |
| image | Sets the image that will be used to build the container. Using this directive assumes that the specified image already exists either on the host or on Docker Hub. |
| build | This directive can be used instead of image. Specifies the location of the Dockerfile that will be used to build this container. |
| db | In the case of the example Dockercompose file, db is a variable for the container you are about to define. |
| restart | Tells the container to restart if the system restarts. |
| volumes | Mounts a linked path on the host machine that can be used by the container |
| environment | Define environment variables to be passed in to the Docker run command. |
| depends_on | Sets a service as a dependency for the current block-defined container |
| port | Maps a port from the container to the host in the following manner: host:container |
| links | Link this service to any other services in the Docker Compose file by specifying their names here. |
