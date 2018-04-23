# dbjob_cron

sudo -i

ns=pro

export ns

cat dbjob_cron.yaml | sed "s/\$NAMESPACE/$ns/" > dbjob_cron-$ns.yaml


kubectl create -f ./dbjob_cron-$ns.yaml


kubectl get cronjob dbjob_cron

kubectl get jobs --watch

# Replace "hello-4111706356" with the job name in your system
$ pods=$(kubectl get pods --selector=job-name=hello-4111706356 --output=jsonpath={.items..metadata.name})

$ echo $pods
hello-4111706356-o9qcm

$ kubectl logs $pods
Mon Aug 29 21:34:09 UTC 2016
Hello from the Kubernetes cluster

$ kubectl delete cronjob dbjob_cron




$ kubectl config view
kubectl cluster-info
