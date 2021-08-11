### Pod-to-pod networking

- Each pod in a Kubernetes node gets assigned a dedicated IP address with a dedicated namespace.
- Pods on a node can communicate with all pods on all nodes without NAT.
- Agents on a node (system daemons, kubelet) can communicate with all the pods on that specific node.

#### Communication between pods in the same node -
<br><br>
<img src="https://user-images.githubusercontent.com/61199820/128997429-bd4d063a-0697-4e5c-98ed-09daab22562a.png" align="left" height="348" width="348" >

<br><br><br><br><br><br><br><br><br><br><br><br><br><br> <br><br>


#### Communication between pods in different nodes -
<br><br>
<img src="https://user-images.githubusercontent.com/61199820/128999648-311e93bd-19c7-447c-8f71-28ad424b5966.png" align="left" height="448" width="548" >
<br><br><br><br><br><br><br><br><br><br><br><br><br><br> <br><br><br><br><br><br>


Example-  

Give direct IP Address in code  || http://10.99.104.153/sso/get-password/       `not recommended `  
or  
Create a service and use the service mapping as shown below   

           env:
              - name: SSO_ADDRESS
              # value: "10.99.104.153"
              value: "sso-service.default"   
              
http://${process.env.SSO_ADDRESS}/get-password/

Code-  

           apiVersion: v1
           kind: Service
           metadata:
             name: sso-service
           spec:
             selector:
               app: sso
             type: ClusterIP
             ports:
               - protocol: TCP
                 port: 80
                 targetPort: 80
                 
            ---
            sso-deployment.yamal
            ---
            login-service.yaml
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
                      image: leenabhavnani/login:1.0
                      env:
                        - name: SSO_ADDRESS
                          # value: "10.99.104.153"
                          value: "sso-service.default"
