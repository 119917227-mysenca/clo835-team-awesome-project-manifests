# clo835-team-awesome-project-manifests


### Create EBS driver addon 
```
eksctl create addon --name aws-ebs-csi-driver --cluster my-cluster --service-account-role-arn arn:aws:iam::407373101635:role/AmazonEKS_EBS_CSI_DriverRole --force
```
