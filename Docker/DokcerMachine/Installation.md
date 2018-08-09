
Reference: https://docs.docker.com/machine/install-machine/#install-machine-directly

    base=https://github.com/docker/machine/releases/download/v0.14.0 &&
      curl -L $base/docker-machine-$(uname -s)-$(uname -m) >/tmp/docker-machine &&
      sudo install /tmp/docker-machine /usr/local/bin/docker-machine
      
      docker-machine version
      
### Example: Create an AWS EC2 instance using docker-machine.

Refer: https://docs.docker.com/machine/

    docker-machine create --driver amazonec2 --amazonec2-access-key AKIAJHQJXNLTPDR2QXKA --amazonec2-secret-key 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 --amazonec2-open-port 8000 --amazonec2-region us-east-2 aws-sandbox
