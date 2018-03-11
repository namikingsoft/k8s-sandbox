# Sandbox of k8s on GKE

```bash
curl https://sdk.cloud.google.com | bash
gcloud auth login
gcloud config set project name_of_project
gcloud config set project name_of_project
gcloud config set compute/zone name_of_region
gcloud container clusters get-credentials name_of_cluster
gcloud components install kubectl
```

## nginx
```bash
kubectl create -f nginx.yaml
kubectl delete -f nginx.yaml
```

## job
```bash
kubectl create -f job.yaml
kubectl delete -f job.yaml

kubectl run pi --image=perl --restart=OnFailure --\
  perl -Mbignum=bpi -wle 'print bpi(2000)'
kubectl delete job --all
```

## run foreground
```bash
kubectl run -i --tty busybox --image=busybox --restart=Never --rm
kubectl run -i --tty busybox --image=busybox --restart=Never --rm -- ls
```
