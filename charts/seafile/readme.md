# seafile
![Version](https://img.shields.io/badge/Version-0.1.1-informational?style=flat-square)
![AppVersion](https://img.shields.io/badge/AppVersion-9.0.10-informational?style=flat-square)

see [seafile deploy](https://manual.seafile.com/docker/deploy_seafile_with_docker/)

# usage
```bash
helm repo add eleksbai https://eleksbai.github.io/helm-charts 
helm show values eleksbai/seafile > my-seafile-value.yaml
# change it !!!
vim my-seafile-value.yaml
helm install -f my-seafile-value.yaml my-seafile  eleksbai/seafile

```
# images
| image                           | tag    |
|---------------------------------|--------|
| docker.io/library/memcached     | 1.6    |
| docker.io/library/mariadb       | 10.6   |
| docker.io/seafileltd/seafile-mc | 9.0.10 |

# values
```yaml
# dbRootPassword is mysql db password
dbRootPassword: "YOU_PASSWORD"
# port is seafile port
port: 8090
# adminEmail
adminEmail: "admin@example.com"
# adminPassword
adminPassword: "YOU_PASSWORD"
# serverLetsencrypt is  SEAFILE_SERVER_LETSENCRYPT, set ( "false" | "true" )
serverLetsencrypt: "false"
# serverHostname is SEAFILE_SERVER_HOSTNAME
serverHostname: "seafile.example.com"
# timezone
timezone: Asia/Shanghai

# not support limit if STORAGE CLASS use  local-path
# storageDb is mysql storage size
storageDb: 10G
# storageSeafile size
storageSeafile: 500Gi
```

# change-pv-reclaim-policy
https://kubernetes.io/docs/tasks/administer-cluster/change-pv-reclaim-policy/
```bash
kubectl get pv
kubectl patch pv <your-pv-name> -p '{"spec":{"persistentVolumeReclaimPolicy":"Retain"}}'
# reuse
kubectl patch pv <your-pv-name>  -p '{"spec":{"claimRef": null}}'

```

# todo
1. default password use generale password.


