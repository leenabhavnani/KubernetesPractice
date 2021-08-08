
### Configure a Pod to Use a PersistentVolume for Storage

https://kubernetes.io/docs/tasks/configure-pod-container/configure-persistent-volume-storage/

### ConfigMap and Secret Volume with Mosquitto

    kubectl apply -f mosquitto-without-volume.yaml  
    kubectl get all  
    kubeclt exec -it pod/mosquitto-67c9bd7cb6-fbl6s /bin/sh  
    ls  
    cd mosquitto  
    cd config/  
    cat mosquitto.conf
    
    kubectl apply -f mosquitto-with-volume.yaml
    // repeat above steps
    cat mosquitto/secret/secret.file
    
