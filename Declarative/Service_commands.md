### Creating a service

    kubectl apply -f my_nginx_depl.yaml
    kubectl get pods -l run=my-nginx -o wide

    kubectl expose deployment/my-nginx

    // This is equivalent to kubectl apply -f the yaml: my_nginx_service
    
    kubectl get svc my-nginx
    kubectl describe svc my-nginx
    kubectl get endpoints
    kubectl get ep my-nginx
    
    kubectl exec my-nginx-75897978cd-clnh6 -- printenv | grep SERVICE
    
    kubectl scale deployment my-nginx --replicas=0;
    kubectl scale deployment my-nginx --replicas=2;
    kubectl get pods -l run=my-nginx -o wide
    kubectl exec my-nginx-75897978cd-9zst8 -- printenv | grep SERVICE
