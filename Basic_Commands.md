### Minikube commands -

    minikube start --kubernetes-version='1.17.4'  
    minikube ip  
    minikube stop  
    minikube status  
    minikube addons list   

### Kubectl commands -

    kubectl version  
    kubectl cluster-info  
    kubectl top // Metrics
    kubectl get nodes   
    kubectl get all  

#### Create and run a particular image in a pod.  

    kubectl run my-nginx --image=nginx  
    kubectl get pods  
    kubectl get pods -o wide  
    kubectl get all  
    kubectl get events
    kubectl config view
       
#### Create a deployment   
    kubectl create deployment nginx-dep --image=nginx   
    kubectl get deployment   
    kubectl get replicaset   
    kubectl edit deployment nginx-dep   
    
    kubectl create deployment my-apache --image=httpd
    kubectl get pods -w
    kubectl scale deployment my-apache --replicas 2
    kubectl logs deployment/my-apache  // only 1 pod at a time
    kubectl logs -l run=my-apache  //only 5 pods at a time but can be increased
    kubectl describe pod {pod-name}
    kubectl delete pod/{pod-name}
    
    kubectl delete deployment nginx-dep
    kubectl delete deployment my-apache
    
#### Debug
    kubectl logs {pod-name}   
    kubectl exec -it {pod-name} -- bin/bash   

#### Addons   
    minikube addons list   
    minikube addons enable metrics-server   
    kubectl get pod,svc -n kube-system   
    minikube addons disable metrics-server  
    

