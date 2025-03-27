# Assignment 2.15


## 1. What is needed to authorize your EC2 to retrieve secrets from AWS Secrets Manager?

To authorize an EC2 instance to retrieve secrets from AWS Secrets Manager, you need to:
1. Create an **IAM role** with the necessary **permissions** (secretsmanager:GetSecretValue).
2. Attach this IAM role to the EC2 instance.
3. Ensure the EC2 instance has the **instance profile** to assume the IAM role and access the secret.

## 3. Using the secret name prod/cart-service/credentials, derive a sensible ARN as the specific resource for access.
ARN:

arn:aws:secretsmanager:us-east-1:255945442255:secret:prod/cart-service/credentials-??????

*where the question marks shows the random numbers generated



## 2. Derive the IAM policy (i.e. JSON)

IAM policy that allows access to retrieve a secret:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "secretsmanager:GetSecretValue",
      "Resource": "arn:aws:secretsmanager:us-east-1:255945442255:secret:prod/cart-service/credentials-??????"
    }
  ]
}




