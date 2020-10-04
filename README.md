# KUBECTL GRAB RESOURCES
**kubectl grab-resources** command collects all resources from the cluster based on **label** input and export to a single YAML file.

# Table of Contents
1. [**Why?**](#why)
2. [**Requirements**](#requirements)
3. [**How to install?**](#how-to-install)
4. [**How to use?**](#how-to-use)
5. [**Export your entire deployment**](#export-your-entire-deployment)
6. [**Restore your deployment**](#restore-your-deployment)
7. [**Demo**](#demo)

## **Why**
Simple command to collect all resources related to a specific label saving the output to a single YAML file.  
Later, users can just use ***kubectl apply -f filename.yaml*** to **restore the resources**.

## **Requirements**  
- [kubectl cli](https://github.com/kubernetes/kubectl)  
- [Krew package manager for kubectl](https://github.com/kubernetes-sigs/krew)      
- [neat plugin for kubectl](https://github.com/itaysk/kubectl-neat)  

## **How to install?**
After installing krew and neat plugin, just copy kubectl-grab_resources to your $PATH/bin

## **How to use?**
  ```
  $ kubectl grab-resources -l LABEL_NAME -o OUTPUT_FILENAME.yaml
  ```

## **Restore your resources**
  ```
  $ kubectl grab-resources -l app=kibana -o kibana-2020-09-16-00:10:25.yaml
  ```
  **Example**(s):  
  - *user deleted kibana resources by mistake*  
 
  ```
  Restoring:  
  $ kubectl apply -f kibana-2020-09-16-00:10:25.yaml
  ```
## Demo
### grab-resources argocd  
[![asciicast](https://asciinema.org/a/Vsz0HJSSryCCvwEqOFycFdO2Q.svg)](https://asciinema.org/a/Vsz0HJSSryCCvwEqOFycFdO2Q)

### grab-resources Kibana  
[![asciicast](https://asciinema.org/a/JAhrlIUjiCAfRu62my4fzVcLI.svg)](https://asciinema.org/a/JAhrlIUjiCAfRu62my4fzVcLI)
