# dbjob_cron

sudo -i

ns=pro

export ns

cat dbjob_cron.yaml | sed "s/\$NAMESPACE/$ns/" > dbjob_cron-$ns.yaml


kubectl create -f ./dbjob_cron-$ns.yaml
