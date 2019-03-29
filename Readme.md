
Create a free dns at https://my.freenom.com/
Create a public hosted zone in rotute53
Update nameservers in freenom with route53 nameservers


export KOPS_CLUSTER_NAME=kubernetes-test.ga
export KOPS_STATE_STORE=s3://kubernetes-test.dev.example.com



kops create cluster \
--node-count=2 \
--node-size=t2.large \
--master-size=t2.micro \
--zones=eu-central-1a \
--name=${KOPS_CLUSTER_NAME}


kops update cluster --name=${KOPS_CLUSTER_NAME} --yes

