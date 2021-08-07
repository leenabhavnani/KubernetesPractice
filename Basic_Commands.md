### Minikube commands -

    minikube start --kubernetes-version='1.17.4'  
    minikube ip  
    minikube stop  
    minikube status  
    minikube addons list   

### Kubectl commands -

    kubectl version  
    kubectl cluster-info  

#### Create and run a particular image in a pod.  

    kubectl run my-nginx --image=nginx  
    kubectl get pods  
    kubectl get pods -o wide  
    kubectl get all  
