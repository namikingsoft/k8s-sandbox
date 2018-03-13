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

## cluster

```bash
gcloud beta container clusters create clustertest \
  --zone us-central1-a \
  --machine-type n1-standard-1 \
  --enable-autoscaling \
  --min-nodes 1 \
  --max-nodes 5 \
  --disk-size 10 \
  --preemptible
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

# foreground
kubectl run sh --image=busybox -it --attach --rm --restart=OnFailurer -- sh
```

## pod
```bash
kubectl run sh -it --attach --image=busybox --restart=Never --rm -- sh
```
