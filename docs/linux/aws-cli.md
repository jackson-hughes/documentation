# AWS CLI

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