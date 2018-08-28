### Step-1 Install docker engine.

### Install docker-machine.

* Crete 3 docker hosts using docker-machine.
  
      docker-machine create --driver amazonec2 --amazonec2-access-key AKIA************** --amazonec2-secret-key KVuog**************VEOChrjML --amazonec2-vpc-id vpc-0238**********107 --amazonec2-subnet-id subnet-0ff8**********3b9fa --amazonec2-region us-east-2 --amazonec2-zone "a" docker-manager1

      docker-machine create --driver amazonec2 --amazonec2-access-key AKIA************** --amazonec2-secret-key KVuog**************VEOChrjML --amazonec2-vpc-id vpc-0238**********38107 --amazonec2-subnet-id subnet-0ff85**********b9fa --amazonec2-region us-east-2 --amazonec2-zone "b" docker-worker1

      docker-machine create --driver amazonec2 --amazonec2-access-key AKIA************** --amazonec2-secret-key KVuog**************VEOChrjML --amazonec2-vpc-id vpc-0238**********38107 --amazonec2-subnet-id subnet-0ff856**********9fa --amazonec2-region us-east-2 --amazonec2-zone "c" docker-worker2


* Swam mode:

