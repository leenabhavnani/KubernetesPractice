### Run the commands is the following order -

      kubectl apply -f mongo-secret.yaml
      kubectl get secret
      kubectl describe secret mongodb-secret

      kubectl apply -f mongo-deploy.yaml
      kubectl get all
      kubectl describe service mongodb-service
      kubectl get pod -o wide

      kubectl apply -f mongo-configmap.yaml
      kubectl get configmaps 
      kubectl describe configmap mongodb-configmap

      kubectl apply -f mongo-express-deploy.yaml 
      kubectl get all

      test it on browser

      minikube service mongo-express-service
