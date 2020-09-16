kubectl **pack** plugin detects your resources from the deployment name provided in the script (in any namespace) and export all requirements in a single YAML. 

**How to use?**
  ```
  $ kubectl pack DEPLOYMENT_NAME
  ```
   
**Export your entire deployment**  
  ```
  $ kubectl pack kibana
  Packed kibana from pvc namespace: monitoring  
  Packed kibana from service namespace: monitoring  
  Packed kibana from secret namespace: monitoring  
  Packed kibana from deployment namespace: monitoring  
  Packed kibana-https from ingressroute namespace: monitoring  
  Exported deployment kibana via kibana-2020-09-16-00:10:25.yaml
  ```
**Restore your deployment**
```
$ kubectl apply -f kibana-2020-09-16-00:10:25.yaml
```
