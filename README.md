# aws-cloudformation-templates
CloudFormation templates from scratch

## Create CloudFormation Stack

aws cloudformation create-stack --stack-name example-cf-stack --template-body file://Practice1.yaml

## Update CloudFormation Stack

aws cloudformation update-stack --stack-name example-cf-stack --template-body file://Practice1.yaml

## Delete Cloudformation Stack

aws cloudformation delete-stack --stack-name example-cf-stack