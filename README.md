kubectl **pack** plugin detects your resources in any namespace and export all requirements in a single YAML. 

**How to use?**
  ```
  $ kubectl pack DEPLOYMENT_NAME
  ```
   
**Export your entire deployment**  
  ```
  $ kubectl pack kibana
  Packed wiki from pvc namespace: default  
  Packed wiki from service namespace: default  
  Packed wiki from secret namespace: default  
  Packed wiki from deployment namespace: default  
  Packed wiki-https from ingressroute namespace: default  
  Exported deployment wiki via kibana-2020-09-16-00:10:25.yaml
  ```
**Restore your deployment**
```
$ kubectl apply -f kibana-2020-09-16-00:10:25.yaml
```
