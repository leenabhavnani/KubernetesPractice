### Configure a Pod to Use a Volume for Storage

An emptyDir volume is first created when a Pod is assigned to a node, and exists as long as that Pod is running on that node. As the name says, the emptyDir volume is initially empty. All containers in the Pod can read and write the same files in the emptyDir volume, though that volume can be mounted at the same or different paths in each container. When a Pod is removed from a node for any reason, the data in the emptyDir is deleted permanently.  

         kubectl apply -f emptydir_volume_depl.yaml
         // or emptydir_volume.yaml   
         kubectl get pods  --watch
         
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
  A hostPath volume mounts a file or directory from the host node's filesystem into your Pod.  
   #### Volume:
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
  #### Persistent Volume:
         mkdir /mnt/data  
         sudo sh -c "echo 'Hello from Kubernetes storage' > /mnt/data/index.html"
         cat /mnt/data/index.html
         kubectl apply -f hostpath_persistent_volume_depl.yaml
         kubectl get pv task-pv-volume
         kubectl get all
         kubectl exec -it <pod name> -- /bin/bash
         apt update
         apt install curl
         curl http://localhost/
  
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
    
