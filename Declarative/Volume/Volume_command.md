### Configure a Pod to Use a Volume for Storage


         kubectl apply -f emptydir_volume_depl.yaml
         // or emptydir_volume.yaml   
         kubectl get pod redis --watch
         
         //New Terminal
         kubectl exec -it redis -- /bin/bash  
         cd /data/redis/
         echo Hello > test-file
         apt-get update
         apt-get install procps
         ps aux 
         kill <pid> 
         // Check the other terminal to track the container state
         kubectl exec -it redis -- /bin/bash
         cd /data/redis/
         ls
         kubectl delete pod redis
         
 https://kubernetes.io/docs/tasks/configure-pod-container/configure-volume-storage/  
         
### Configure a Pod to Use a Volume/PersistentVolume for Storage using hostPath

         kubectl apply -f hostpath_volume_depl.yaml
         kubectl get all
         cd /data/
         echo Hello > test-file
         cat test-file
         kubectl exec -it <pod name> bash
         cd /data/redis/
         cat test-file
         exit
         kubectl delete <pod name>
         kubectl get all
         kubectl exec -it <new pod name> bash
         cd /data/redis/
         cat test-file
         exit

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
    
