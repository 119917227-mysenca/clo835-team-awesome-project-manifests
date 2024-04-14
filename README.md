# clo835-team-awesome-project-manifests


### Create EBS driver addon 
```
eksctl create addon --name aws-ebs-csi-driver --cluster clo835-final --service-account-role-arn arn:aws:iam::407373101635:role/AmazonEKS_EBS_CSI_DriverRole --force
```

### Set up ECR secret
Create secret for ECR authentication using ~/.docker/config.json
```
cd ~/.docker

kubectl create secret generic creds --from-file=.dockerconfigjson=./config.json --type=kubernetes.io/dockerconfigjson -n final

```

### Set up AWS secret

Create AWS secrets for downloading S3 image
```
export aws_access_key_id=[Your aws_access_key_id]
export aws_secret_access_key=[Your aws_secret_access_key]
export aws_session_token=[Your aws_session_token]

kubectl create secret generic aws-credentials \
    --from-literal=AWS_ACCESS_KEY_ID=$aws_access_key_id \
    --from-literal=AWS_SECRET_ACCESS_KEY=$aws_secret_access_key \
    --from-literal=AWS_SESSION_TOKEN=$aws_session_token
```