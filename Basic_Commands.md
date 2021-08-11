### Minikube commands -

    minikube start --kubernetes-version='1.17.4'  
    minikube ip  
    minikube stop  
    minikube status  
    minikube addons list   
    kubectl config view  

### Kubectl commands -

    kubectl version  
    kubectl cluster-info  
    kubectl top pod // Metrics after enabling the addon
    kubectl get nodes   
    kubectl get all  

#### Create and run a particular image in a pod.  

    kubectl run my-nginx --image=nginx  
    kubectl get pods  
    kubectl get pods -o wide  
    kubectl get all  
    kubectl get events      
    kubectl delete deployment my-nginx
       
#### Create a deployment   
    kubectl create deployment nginx-dep --image=nginx   
    kubectl get deployment   
    kubectl get replicaset   
    kubectl get services
    kubectl describe pod {pod-name}
    kubectl describe deployment {deployment-name}
    kubectl edit deployment nginx-dep   
    
    kubectl create deployment my-apache --image=httpd
    kubectl get all
    kubectl get all -l app=my-apache
    
    kubectl get pods -w  //watch the changes of scaling
    kubectl scale deployment my-apache --replicas 2
    kubectl logs deployment/my-apache  // only 1 pod at a time
    kubectl logs -l app=my-apache  //only 5 pods at a time but can be increased
    kubectl describe pod {pod-name}
    kubectl delete pod {pod-name}
    
    kubectl exec -it pod-name bash  
    curl localhost:80
    
    //outside the pod
    curl ip_address_of_pod:80
    
    kubectl set image deployment/my-apache httpd=httpd:2.4.12  
    kubectl rollout status deployment.apps/my-apache  
    kubectl rollout history deployment.apps/my-apache  
    kubectl rollout history deployment.apps/my-apache --revision=3
    kubectl rollout undo deployment.apps/my-apache
    kubectl rollout status deployment.apps/my-apache  
    
    kubectl get deployments nginx-dep --export -o yaml
    kubectl get deployments nginx-dep --export -o json
    kubectl delete deployment nginx-dep
    kubectl delete deployment my-apache
    
#### Service
    kubectl expose deployment/my-apache --port 80
    kubectl get all
    curl service_ip:80
    
### Dry Run
    kubectl create deployment test --image nginx --dry-run -o yaml
    kubectl expose deployment/test --port 80 --dry-run -o yaml
    
#### Debug
    kubectl logs {pod-name}   
    kubectl exec -it {pod-name} -- bin/bash   

#### Addons   
    minikube addons list   
    minikube addons enable metrics-server   
    kubectl top pod  
    kubectl get pod,svc -n kube-system   
    minikube addons disable metrics-server  
    
#### Curl installation

     apt update  
     apt install curl  
     or  
     cat /etc/os-release
     apk add curl //alpine
    

