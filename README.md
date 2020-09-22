# KUBECTL GRAB RESOURCES
**kubectl grab-resources** command collects all resources based on **label**.

# Table of Contents
1. [**Why?**](#why)
2. [**Requirements**](#requirements)
3. [**How to use?**](#how-to-use)
4. [**Export your entire deployment**](#export-your-entire-deployment)
5. [**Restore your deployment**](#restore-your-deployment)
6. [**Demo**](#demo)

## **Why**
Simple command to collect all resources related to a specific label saving the output to a single YAML file.
Later, users can just use ***kubectl apply -f filename.yaml*** to **restore the resources**.

## **Requirements**  
- [kubectl cli](https://github.com/kubernetes/kubectl)  
- [Krew package manager for kubectl](https://github.com/kubernetes-sigs/krew)      
- [neat plugin for kubectl](https://github.com/itaysk/kubectl-neat)  

## **How to use?**
  ```
  $ kubectl grab-resources LABEL_NAME
  ```

## **Restore your resources
  ```
  $ kubectl grab-resources kibana
  $ kubectl apply -f kibana-2020-09-16-00:10:25.yaml
  ```
## Demo
### grab-resources speedtest  
show speedtest asciimovie

### grab-resources Kibana  
show kibana asciimovie
