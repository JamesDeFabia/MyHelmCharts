This repo contains some Helm charts (yaml files) that do various things. 
Their main purpose is to use in documentation projects, but some were used 
to help me learn HELM and yaml. 
They all modify the HPCC/HPCC base chart.  

LIST OF CHARTS
==============
**tworoxies.yaml**

This chart adds a second roxie to a default system. It can be used in conjunction with 
one of the persistent storage charts. 
```
#assumes you have a d drive with the appropriate folders 
helm install mylocalfile hpcc/hpcc-localfile --set common.hostpath=/run/desktop/mnt/host/d/hpccdata 
# capture the output from storage: on to mystorage.yaml
helm upgrade --install mycluster hpcc/hpcc -f mystorage.yaml -f tworoxies.yaml
```
**noroxie.yaml**

This chart removes roxie and the roxie-workunit eclagent It can be used in conjunction with 
one of the persistent storage charts. 
```
#assumes you have a d drive with the appropriate folders 
helm install mylocalfile hpcc/hpcc-localfile --set common.hostpath=/run/desktop/mnt/host/d/hpccdata 
# capture the output from storage: on to mystorage.yaml
helm upgrade --install mycluster hpcc/hpcc -f mystorage.yaml -f noroxie.yaml
```


**twothors.yaml**

This chart adds a second Thor cluster with 10 workers. It can be used in conjunction with 
one of the persistent storage charts. 
```
#assumes you have a d drive with the appropriate folders 
helm install mylocalfile hpcc/hpcc-localfile --set common.hostpath=/run/desktop/mnt/host/d/hpccdata 
#capture the output from storage: on to mystorage.yaml
helm upgrade --install mycluster hpcc/hpcc -f mystorage.yaml -f twothors.yaml
```

**threethorsonelinger.yaml**

This chart adds a second and third Thor cluster with 10 workers. However, the third one has lingerPeriodset to 30 seconds.  It can be used in conjunction with 
one of the persistent storage charts. 
```
#assumes you have a d drive with the appropriate folders 
helm install mylocalfile hpcc/hpcc-localfile --set common.hostpath=/run/desktop/mnt/host/d/hpccdata 
#capture the output from storage: on to mystorage.yaml
helm upgrade --install mycluster hpcc/hpcc -f mystorage.yaml -f threethorsonelinger.yaml
```

**nothor.yaml**

This chart removes thor. It can be used in conjunction with 
one of the persistent storage charts. 
```
#assumes you have a d drive with the appropriate folders 
helm install mylocalfile hpcc/hpcc-localfile --set common.hostpath=/run/desktop/mnt/host/d/hpccdata 
# capture the output from storage: on to mystorage.yaml
helm upgrade --install mycluster hpcc/hpcc -f mystorage.yaml -f nothor.yaml
```
