# dbjob_cron

ns=pro
export ns
sudo -i
cat dbjob_cron.yaml | sed "s/\$NAMESPACE/$ns/" > dbjob_cron-$ns.yaml

kubectl create -f ./dbjob_cron-$ns.yaml
