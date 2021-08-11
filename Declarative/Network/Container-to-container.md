### Container-to-container networking

 - In the most basic configurations, container to container communication within a single pod takes place via the **localhost and port numbers**. 
 - This is possible because the containers in the pod are located in the **same network namespace**.


Example -  
http://localhost/sso/get-password/   
or  
http://${process.env.SSO_ADDRESS}/get-password/  
         
         env:
            - name: SSO_ADDRESS
              value: localhost


![image](https://user-images.githubusercontent.com/61199820/128996226-8718be77-2df2-4cc9-940d-22b66427a04d.png)
