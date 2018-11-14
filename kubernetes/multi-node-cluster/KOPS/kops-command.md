
Ex: kops create cluster

       kops create cluster \
        --node-count 3 \
        --zones us-west-2a,us-west-2b,us-west-2c \
        --master-zones us-west-2a,us-west-2b,us-west-2c \
        --node-size t2.medium \
        --master-size t2.medium \
        --topology private \
        --networking kopeio-vxlan \
        hacluster.example.com
