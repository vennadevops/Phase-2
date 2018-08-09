
* Reference for docker-machine installation: https://docs.docker.com/machine/install-machine/#install-machine-directly
* Reference for docker machine docs: https://docs.docker.com/machine/
* Referecne for Docker with AWS example: https://docs.docker.com/machine/drivers/aws/
* Referecne for Docker with AWS example: https://stackoverflow.com/questions/45658541/docker-machine-connect-to-existing-aws-machine/46228588#46228588
* Referecne for Docker with AWS example: http://docker-k8s-lab.readthedocs.io/en/latest/docker/docker-machine-aws.html

### Installtion on Ubuntu:

    base=https://github.com/docker/machine/releases/download/v0.14.0 &&
      curl -L $base/docker-machine-$(uname -s)-$(uname -m) >/tmp/docker-machine &&
      sudo install /tmp/docker-machine /usr/local/bin/docker-machine
      
      docker-machine version
      
### Example: Create an AWS EC2 instance using docker-machine.

#### We need to follow the below steps.

* Creare IAM in AWS.  Refer: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/get-set-up-for-amazon-ec2.html#create-an-iam-user
    * Services --> Security, Identity & Compliance --> IAM --> Users --> Add User.
    * Provide Username.
    * Check this box "AWS Management Console access".
    * Choose "Custom password" and enter the password. (check the box "show passowrd" to check what you are typing.)
    * Uncheck the box "Users must create a new password at next sign-in". and then click on the button "Next: Permissions"
    * Create Group.
    * Give the group name.
    * Choose "AdministratorAccess" from the list of policies. and then click on the button "Next: Review"
    * Finally click on "Create User" button.
    
* Create access key & secret key for the IAM user.
    * Go to Users --> Security Credentials --> Create Access Key --> Copy the Access Key Id & Secret Access Key.
* Run the below command

    docker-machine create --driver amazonec2 --amazonec2-access-key ${Access Key Id} --amazonec2-secret-key ${Secret Access Key} --amazonec2-open-port 8000 --amazonec2-region us-east-2 aws-sandbox
    
By default ubuntu image will be installed on the instance. Give the Redhat Linux amazon AMI to create an instance with redhat os.
    
    docker-machine create --driver amazonec2 --amazonec2-access-key ${Access Key Id} --amazonec2-secret-key ${Secret Access Key} --amazonec2-open-port 8000 --amazonec2-region us-east-2 --amazonec2-ami ami-03291866 aws-sandbox21
    
    
