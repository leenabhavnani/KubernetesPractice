### Commands to execute:

    kubectl api-resources

    kubectl api-versions

    kubectl explain pod --recursive

    kubectl explain services --recursive
    kubectl explain  services.spec
    kubectl explain  services.spec.type

    kubectl explain deployments --recursive  //too much info
    kubectl explain deployment.spec.template.spec.volumes.nfs.server
    
    kubectl apply -f my_nginx_depl.yaml
    kubectl create -f my_nginx_service.yaml
    curl <IP>:80
    
    kubectl get deployment my-nginx -o yaml   //check the status
    
    kubectl delete -f my_nginx_depl.yaml
    kubectl delete -f my_nginx_service.yaml
    
    kubectl apply -f my_nginx_pod.yaml
    
 https://kubernetes.io/docs/reference/#api-reference
 
