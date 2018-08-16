
Reference: https://kubernetes.io/docs/getting-started-guides/ubuntu/installation/

# Launch an AWS Ubuntu machine and login as route user.

# 1. Add the cloud & credentials

  * Command: juju add-credential aws

        Output:

        root@ip-172-31-2-89:~# juju add-credential aws
        Enter credential name: my_aws_creds

        Using auth-type "access-key".

        Enter access-key: AKIA********EVTOIQ


        Enter secret-key:

        Credential "my_aws_creds" added locally for cloud "aws".

#2. Create an instance on AWS EC2. A new instance will be created in AWS with the instance name 'juju-controller-machine-0' and machine type t2.medium.

	* Command: juju bootstrap aws/us-east-2
  
![image](https://user-images.githubusercontent.com/24622526/44193393-2d8d6000-a122-11e8-8515-541f9dcf80f8.png)
