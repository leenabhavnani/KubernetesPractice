### Internet-to-service networking

 The most common method used to handle traffic is by using a load balancer.  
 In Kubernetes, we can configure load balancers. When a service is created, users can:  

  - Specify a load balancer that will expose the IP address of the load balancer.
  - Direct traffic to the load balancer and communicate with the service through it.


        apiVersion: v1  
        kind: Service   
        metadata:  
          name: login-service  
        spec:  
          selector:  
            app: login  
          type: LoadBalancer  
          ports:  
            - protocol: TCP  
              port: 8080  
              targetPort: 8080  
      
        ---
        apiVersion: apps/v1
        kind: Deployment
        metadata:
          name: login-deployment
        spec:
          replicas: 1
          selector: 
            matchLabels:
              app: login
          template:
            metadata:
              labels:
                app: login
            spec:
              containers:
                - name: login
                  image: leenabhavnani/login:1.0 `
                  
                  
