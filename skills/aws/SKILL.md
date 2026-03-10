---
name: aws
description: "AWS CLI - manage S3, EC2, Lambda, IAM, CloudFormation and other AWS services. Use when user mentions 'aws', 'amazon web services', 's3', 'ec2', 'lambda', or wants to interact with AWS."
category: devtools
install_command: "brew install awscli"
binary: aws
---

# aws

## Setup

```bash
brew install awscli
```

Verify installation:
```bash
aws --version
```

Use `--output json` for machine-readable output.

## Authentication

```bash
aws configure
```

Verify identity:
```bash
aws sts get-caller-identity
```

## Resources

### S3

| Command | Description |
|---------|-------------|
| `aws s3 ls` | List all buckets |
| `aws s3 ls s3://<bucket>` | List objects in a bucket |
| `aws s3 ls s3://<bucket>/<prefix>/ --recursive` | List all objects with a prefix |
| `aws s3 cp <file> s3://<bucket>/` | Upload a file to S3 |
| `aws s3 cp s3://<bucket>/<key> <file>` | Download a file from S3 |
| `aws s3 sync . s3://<bucket>/` | Sync local directory to S3 |
| `aws s3 sync s3://<bucket>/ .` | Sync S3 to local directory |
| `aws s3 rm s3://<bucket>/<key>` | Delete an object |
| `aws s3 mb s3://<bucket>` | Create a bucket |
| `aws s3 rb s3://<bucket> --force` | Delete a bucket and its contents |

### EC2

| Command | Description |
|---------|-------------|
| `aws ec2 describe-instances` | List all EC2 instances |
| `aws ec2 describe-instances --filters "Name=instance-state-name,Values=running"` | List running instances |
| `aws ec2 start-instances --instance-ids <id>` | Start an instance |
| `aws ec2 stop-instances --instance-ids <id>` | Stop an instance |
| `aws ec2 terminate-instances --instance-ids <id>` | Terminate an instance |
| `aws ec2 describe-security-groups` | List security groups |

### Lambda

| Command | Description |
|---------|-------------|
| `aws lambda list-functions` | List all Lambda functions |
| `aws lambda invoke --function-name <name> output.json` | Invoke a function |
| `aws lambda invoke --function-name <name> --payload '{"key":"value"}' output.json` | Invoke with payload |
| `aws lambda get-function --function-name <name>` | Get function details |
| `aws lambda update-function-code --function-name <name> --zip-file fileb://function.zip` | Update function code |
| `aws lambda list-event-source-mappings` | List event source mappings |

### IAM

| Command | Description |
|---------|-------------|
| `aws iam list-users` | List all IAM users |
| `aws iam list-roles` | List all IAM roles |
| `aws iam list-policies --scope Local` | List custom policies |
| `aws iam get-user` | Get current user details |
| `aws iam create-user --user-name <name>` | Create a user |

### CloudFormation

| Command | Description |
|---------|-------------|
| `aws cloudformation deploy --template-file template.yaml --stack-name <name>` | Deploy a stack |
| `aws cloudformation describe-stacks` | List all stacks |
| `aws cloudformation describe-stack-events --stack-name <name>` | View stack events |
| `aws cloudformation delete-stack --stack-name <name>` | Delete a stack |

### STS

| Command | Description |
|---------|-------------|
| `aws sts get-caller-identity` | Show current identity |
| `aws sts assume-role --role-arn <arn> --role-session-name <name>` | Assume an IAM role |

## Global Flags

| Flag | Description |
|------|-------------|
| `--output json` | Output as JSON |
| `--output table` | Output as table |
| `--output text` | Output as plain text |
| `--region <region>` | Specify AWS region |
| `--profile <name>` | Use a named profile |
| `--query <expression>` | JMESPath query for filtering output |
| `--no-paginate` | Disable pagination |
