# Login to ECR (replace <region> and <account-id> with your actual values)
$ aws ecr get-login-password --region <region> | docker login --username AWS --password-stdin <account-id>.dkr.ecr.<region>.amazonaws.com

# Login to ECR working command from myside:
$ aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin <account-id>.dkr.ecr.us-east-1.amazonaws.com


# Build the Docker image (replace <repo-name> with your ECR repository name)
$ docker build -t <account-id>.dkr.ecr.<region>.amazonaws.com/<repo-name>:latest .

# Push the Docker image to ECR (replace <repo-name> with your ECR repository name)
$ docker push <account-id>.dkr.ecr.<region>.amazonaws.com/<repo-name>:latest
