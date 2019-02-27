# AWS CLI

## Querying / searching

Query EC2 instances filtered on specific tag

```bash
aws ec2 describe-instances --filter "Name=tag:Name,Values=tagvalue"
```

## SSM

Insert parameter into parameter store

```bash
aws ssm put-parameter --name "$PARAM_NAME" --type SecureString --value "$PARAM_VALUE" --key-id alias/$KMS_KEY_NAME
```

<br>

Retrieve parameter

```bash
aws ssm get-parameter --name "$PARAM_NAME" --with-decryption --region eu-west-2 --output text --query 'Parameter.Value'
```
