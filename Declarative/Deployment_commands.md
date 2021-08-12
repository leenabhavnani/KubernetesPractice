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
    
    kubectl delete -f my_nginx_depl.yaml
    kubectl delete -f my_nginx_service.yaml
    
 https://kubernetes.io/docs/reference/#api-reference
 
