# KUBECTL PACK DEPLOY
**kubectl pack-deploy** detects resources required from running deployments, statefulsets, daemonsets and export it with all dependencies in a single YAML.

# Table of Contents
1. [**Why?**](#why)
2. [**Requirements**](#requirements)
3. [**How to use?**](#how-to-use)
4. [**Export your entire deployment**](#export-your-entire-deployment)
5. [**Restore your deployment**](#restore-your-deployment)
6. [**Demo**](#Demo)

## **Why**
We need a simple ***pack-deploy*** command in **kubectl** that exports **all requirements resources** for the deployments, statefulsets, daemonsets running in the cluster.  

Later, users can just use ***kubectl apply -f filename.yaml*** to **restore the deployment**.

## **Requirements**  
- [kubectl cli](https://github.com/kubernetes/kubectl)  
- [Krew package manager for kubectl](https://github.com/kubernetes-sigs/krew)      
- [neat plugin for kubectl](https://github.com/itaysk/kubectl-neat)  

## **How to use?**
  ```
  $ kubectl get deployment -A
  $ kubectl pack-deploy DEPLOYMENT_NAME
  ```
  
## **Export your entire deployment**  
  ```
  $ kubectl pack-deploy kibana
  Packed kibana from pvc namespace: monitoring  
  Packed kibana from service namespace: monitoring  
  Packed kibana from secret namespace: monitoring  
  Packed kibana from deployment namespace: monitoring  
  Packed kibana-https from ingressroute namespace: monitoring  
  Exported deployment kibana via kibana-2020-09-16-00:10:25.yaml
  ```

## **Restore your deployment**
  ```
  $ kubectl apply -f kibana-2020-09-16-00:10:25.yaml
  ```
== Demo
=== pack-deploy speedtest  
[![asciicast](https://asciinema.org/a/7kHH3cfZtumzwY4BGNZHkqPAX.svg)](https://asciinema.org/a/7kHH3cfZtumzwY4BGNZHkqPAX)

=== pack-deploy Kibana  
[![asciicast](https://asciinema.org/a/I7ila7v7PvS48iXVzWX9Q7YTi.svg)](https://asciinema.org/a/I7ila7v7PvS48iXVzWX9Q7YTi)

