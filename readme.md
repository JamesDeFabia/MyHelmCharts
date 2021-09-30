This repo contains some Helm charts (yaml files) that do various things. 
Their main purpose is to use in documentation projects, but some were used 
to help me learn HELM and yaml. 
They all augment the HPCC base chart.  

LIST OF CHARTS
==============
**TwoRoxies.yaml**

This chart adds a second roxie to a edfault system. It can be used in conjunction with 
one of the persistent storage charts. 
```
helm upgrade --install mycluster hpcc/ --version=8.2.18 -f examples/local/values-localfile.yaml -f myValues.yaml
```
