
* Reference for docker-machine installation: https://docs.docker.com/machine/install-machine/#install-machine-directly
* Reference for docker machine docs: https://docs.docker.com/machine/
* Referecne for Docker with AWS example: https://docs.docker.com/machine/drivers/aws/
* Referecne for Docker with AWS example: https://stackoverflow.com/questions/45658541/docker-machine-connect-to-existing-aws-machine/46228588#46228588
* Referecne for Docker with AWS example: http://docker-k8s-lab.readthedocs.io/en/latest/docker/docker-machine-aws.html

### Install docker-machine on Ubuntu:

    base=https://github.com/docker/machine/releases/download/v0.14.0 &&
      curl -L $base/docker-machine-$(uname -s)-$(uname -m) >/tmp/docker-machine &&
      sudo install /tmp/docker-machine /usr/local/bin/docker-machine
      
      docker-machine version
      
### Example: Create an AWS EC2 instance using docker-machine.

#### Follow the below steps.

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

        docker-machine create --driver amazonec2 --amazonec2-access-key ${Access Key Id} --amazonec2-secret-key ${Secret Access Key} --amazonec2-open-port 8000 --amazonec2-region us-east-2 aws-sandbox20
    
By default ubuntu image will be installed on the instance. Give the Redhat Linux amazon AMI to create an instance with redhat os.
    
    docker-machine create --driver amazonec2 --amazonec2-access-key ${Access Key Id} --amazonec2-secret-key ${Secret Access Key} --amazonec2-open-port 8000 --amazonec2-region us-east-2 --amazonec2-ami ami-03291866 aws-sandbox21

Go to EC2 instances: 

![image](https://user-images.githubusercontent.com/24622526/43895229-0f2f6238-9bc4-11e8-9f96-6e4473041f9e.png)

#### docker-machine ls
    
![image](https://user-images.githubusercontent.com/24622526/43895159-ddf1d836-9bc3-11e8-8e71-ee14adc928c7.png)

### Connect to the AWS machines which were created by docker-machine.

#### Using docker: docker-machine ssh aws-sandbox20

![image](https://user-images.githubusercontent.com/24622526/43895278-47288282-9bc4-11e8-80d3-41d10877c9ff.png)

#### from local git bash:

    docker-machine inspect aws-sandbox20
    
![image](https://user-images.githubusercontent.com/24622526/43895396-b703c8b4-9bc4-11e8-892b-70b05073945a.png)

    
    
