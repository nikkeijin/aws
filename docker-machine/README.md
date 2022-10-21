# Install Homebrew

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

# Install and setup AWS CLI

```
brew install awscli 
aws configure
```

# Install docker-machine

```
brew install docker-machine
```

# Setup EC2 instance with default zone OR specifc zone & VPC

> EC2 with Default Zone & VPC

```
docker-machine create --driver amazonec2 --amazonec2-instance-type "t2.small" --amazonec2-region "ap-northeast-1" testmachine
```

> EC2 with Specific Zone & VPC

```
docker-machine create --driver amazonec2 --amazonec2-zone c --amazonec2-instance-type "t2.small" --amazonec2-region "ap-northeast-1" --amazonec2-ssh-user "ubuntu" --amazonec2-vpc-id "vpc-00000000000000000" testmachine
```

# Connect into a machine

```
docker-machine env testmachine
eval $(docker-machine env testmachine)
```

# Setup inbound rules to use custom port

Security group > inbound - > port

# Useful commands for docker-machine

https://github.com/Nordstrom/docker-machine/blob/master/docs/drivers/aws.md