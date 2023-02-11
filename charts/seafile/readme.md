# seafile
![Version: 0.1.1](https://img.shields.io/badge/Version-3.1.2-informational?style=flat-square) ![AppVersion: 9.0.10](https://img.shields.io/badge/AppVersion-8.0.7-informational?style=flat-square)
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


