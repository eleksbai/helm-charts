# usage
```bash
helm repo add eleksbai https://eleksbai.github.io/helm-charts
helm install my-seafile eleksbai/seafile
helm show values eleksbai/seafile > example-value.ymal
# change it !!!
vim my-seafile-value.yaml
helm install -f my-seafile-value.yaml my-seafile  eleksbai

```

see [seafile deploy](https://manual.seafile.com/docker/deploy_seafile_with_docker/)


# change-pv-reclaim-policy
https://kubernetes.io/docs/tasks/administer-cluster/change-pv-reclaim-policy/
```bash
kubectl get pv
kubectl patch pv <your-pv-name> -p '{"spec":{"persistentVolumeReclaimPolicy":"Retain"}}'
# reuse
kubectl patch pv <your-pv-name>  -p '{"spec":{"claimRef": null}}'

```



