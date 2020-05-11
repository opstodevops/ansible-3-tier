# ansible-3-tier
Code repository for Ansible 3 tier architecture project

### Create a Docker container from Dockerfile
```
docker build --rm -t centos:ansible .
```

### Start AWS Ansible container
```
docker run --rm -t -d --name ansiblecontrolnode --volume "$(pwd)":/ansible --workdir /ansible centos:ansible
```

### Interact with the container
```
docker exec -it ansiblecontrolnode /bin/bash
```

### OR in 1 command like this
```
docker run --rm -it --name ansiblecontrolnode --volume "$(pwd)":/ansible --workdir /ansible centos:ansible
```

### Docker container with AWS ENV VARIABLES
```
docker container run --rm -it --name ansible01 --volume "$(pwd)"/ansible --workdir /ansible --env "AWS_ACCESS_KEY_ID"="awsaccesskeyid" --env "AWS_SECRET_ACCESS_KEY"="awssecretaccesskey" centos:ansible
```

### Deploy the environment
```
ansible-playbook aws_deploy_ansible_3tier.yml
```





