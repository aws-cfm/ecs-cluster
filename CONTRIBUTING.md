# Contributor Guide

## Generate ECS RegionMap

To update the region map execute the following lines in your terminal:

```
$ regions=$(aws ec2 describe-regions --query "Regions[].RegionName" --output text)
$ image_name=amzn2-ami-ecs-hvm-2.0.20190510-x86_64-ebs
$ for region in $regions; do ami=$(aws --region $region ec2 describe-images --filters "Name=name,Values=$image_name" --query "Images[0].ImageId" --output "text"); printf "'$region':\n  ECSAMI: '$ami'\n"; done
```

You can get image name from https://docs.aws.amazon.com/AmazonECS/latest/developerguide/ecs-optimized_AMI.html
