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
          image: leenabhavnani/login:1.0