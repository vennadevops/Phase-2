
A docker-compose.yml file is organized into four sections:


| Project Type | Purpose |
| --- | --- |
| version | Specifies the Compose file syntax version. This guide will use Version 3 throughout. |
| services | In Docker a service is the name for a “Container in production”. This section defines the containers that will be started as a part of the Docker Compose instance. |
| networks | This section is used to configure networking for your application. You can change the settings of the default network, connect to an external network, or define app-specific networks. |
| volumes | Mounts a linked path on the host machine that can be used by the container. |
