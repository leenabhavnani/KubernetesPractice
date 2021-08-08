
## Namespaces

    kubectl get namespace  
    kubectl create namespace kube-demo  
    kubectl describe namespaces kube-system   

   #### Create namespace using config file
    kubectl apply -f namespace_configmap.yaml  
    kubectl describe namespaces kube-demo-ns  
    kubectl get cofigmaps   
    kubectl get configmaps -n kube-demo-ns  
    
    kubectl run nginx --image=nginx --namespace=<insert-namespace-name-here>
    kubectl get pods --namespace=<insert-namespace-name-here>
    kubectl config set-context --current --namespace=<insert-namespace-name-here>
    # Validate it
    kubectl config view --minify | grep namespace:
