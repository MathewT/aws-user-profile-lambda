# AWS User Profile Lambda


## IAM Deployment User Setup
  - create an IAM user (e.g. lambda-deployer)
  - No console login for lambda-deployer
  - Assign key and secret to lambda-deployer
  - Create inline policy for lambda-deployer:
```bash

  {
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "Stmt1488419922000",
            "Effect": "Allow",
            "Action": [
                "lambda:GetFunction",
                "lambda:UpdateFunctionCode",
                "lambda:UpdateFunctionConfiguration"
            ],
            "Resource": [
                "arn:aws:lambda:*"
            ]
        }
    ]
}

```

## Create an IAM Role for Lambda Execution
*NOTE*:  Only assign the minimum set of permissions needed

E.g. lambda-exec-role

Policy:  AWSLambdaExecute


## Create the Lambda via the AWS console

  - Node.js 4.3 runtime
  - Blank template
  - Specify the IAM role (e.g. lambda-exec-role)



```bash

npm install jsonwebtoken  --save-dev

```


## Deployment to AWS

```bash

npm run deploy

```
