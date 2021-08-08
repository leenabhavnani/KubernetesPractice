
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
    kubectl get deployments --namespace=<insert-namespace-name-here>
    
    kubectl config set-context --current --namespace=<insert-namespace-name-here>
    # Validate it
    kubectl config view --minify | grep namespace:

   #### Components not bound with namespace
    # In a namespace
    kubectl api-resources --namespaced=true

    # Not in a namespace
    kubectl api-resources --namespaced=false
    
    
  #### Deleting a namespace  
    kubectl delete namespaces <insert-some-namespace-name>
    Warning: This deletes everything under the namespace!



#### Use cases:

- As a cluster operator, I want to support multiple user communities on a single cluster.   
- As a cluster operator, I want to delegate authority to partitions of the cluster to trusted users in those communities.   
- As a cluster operator, I want to limit the amount of resources each community can consume in order to limit the impact to other communities using the cluster.   
- As a cluster user, I want to interact with resources that are pertinent to my user community in isolation of what other user communities are doing on the cluster   
