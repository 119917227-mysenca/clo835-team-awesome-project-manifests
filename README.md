# clo835-team-awesome-project-manifests

### Set up ECR secret
Create secret for ECR authentication using ~/.docker/config.json
```
cd ~/.docker

kubectl create secret generic creds --from-file=.dockerconfigjson=./config.json --type=kubernetes.io/dockerconfigjson -n final

```

