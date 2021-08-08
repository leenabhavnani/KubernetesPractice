
## Namespaces

    kubectl get namespace  
    kubectl create namespace kube-demo  
    kubectl describe namespaces kube-system   

   #### Create namespace using config file
    kubectl apply -f namespace_configmap.yaml  
    kubectl describe namespaces kube-demo-ns  
    kubectl get cofigmaps   
    kubectl get configmaps -n kube-demo-ns  
