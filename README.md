# aws-static-web-hosting
This repo is to automate the process of hosting a static website using s3 aws developer tools

## To validate template on aws cli
aws cloudformation validate-template --template-body file://main.yml  

## To create cloudformation stack for S3 Bucket on aws cli
aws cloudformation create-stack --stack-name name-fo-your-stack --template-body file://main.yml  

you can specify the IAM role that cloudformation will assume to perform the create with this option:  
--role-arn arn:aws:iam::058264146234:role/CloudFormationStackRole

## To create cloudformation stack for aws codepipeline on aws cli
aws cloudformation create-stack --stack-name codepipeline --template-body file://codepipeline.yml --parameters ParameterKey=S3BucketName,ParameterValue=my-s3-bucket ParameterKey=GitHubRepo,ParameterValue=myuser/myrepo ParameterKey=GitHubToken,ParameterValue=mygithubtoken


