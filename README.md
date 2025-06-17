# Assignment_215_ce10
Assignment 2.15 CE 10 Krisbi

1. What is needed to authorize your EC2 to retrieve secrets from the AWS Secrets Manager?
  To allow an EC2 instance to retrieve secrets from AWS Secrets Manager:

   We need:
a. An IAM role attached to the EC2 instance (via instance profile).

b. The IAM role must have permissions to access the desired secret (either all secrets or specific ones).

c. (Optional but recommended) Limit access to specific secrets and specific actions (e.g., secretsmanager:GetSecretValue).

2. Derive the IAM Policy JSON (to retrieve specific secret)
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "secretsmanager:GetSecretValue",
        "secretsmanager:DescribeSecret"
      ],
      "Resource": "arn:aws:secretsmanager:ap-southeast-1:krisbianto:secret:prod/cart-service/credentials-*"
    }
  ]
}


3. Using the secret name prod/cart-service/credentials, derive a sensible ARN as the specific resource for access
   arn:aws:secretsmanager:ap-southeast-1:krisbianto:secret:prod/cart-service/credentials-a1b2c3
