### Deploy a simple web application using a StatefulSet.

    //To verify ordered pod creation 
    kubectl get pods -w -l app=nginx
    
    //in another terminal
    kubectl apply -f nginx_statefulset.yaml  
    kubectl get all  
    kubectl get service nginx  
    kubectl get statefulset web  
    
    // Execute a container that provides the nslookup command
    kubectl run -i --tty --image busybox:1.28 dns-test --restart=Never --rm
    
    nslookup web-0.nginx
    nslookup web-1.nginx
    
    kubectl get pods -w -l app=nginx
    kubectl delete pod -l app=nginx
    
   #### Storage
    kubectl get pvc -l app=nginx  
    for i in 0 1; do kubectl exec "web-$i" -- sh -c 'echo "$(hostname)" > /usr/share/nginx/html/index.html'; done  
    for i in 0 1; do kubectl exec -i -t "web-$i" -- curl http://localhost/; done  
    
    kubectl get pods -w -l app=nginx
    kubectl delete pod -l app=nginx
    for i in 0 1; do kubectl exec -i -t "web-$i" -- curl http://localhost/; done
    
   #### Scaling  
    kubectl scale sts web --replicas=5  
    kubectl patch sts web -p '{"spec":{"replicas":3}}'
    
    // PersistentVolumes mounted to the Pods are not deleted
    kubectl get pvc -l app=nginx
