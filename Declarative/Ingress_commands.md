
List of Ingress Controllers you can choose from:   
https://kubernetes.io/docs/concepts/services-networking/ingress-controllers/

Ingress Controller Bare Metal:  
https://kubernetes.github.io/ingress-nginx/deploy/baremetal/

Set up Ingress on Minikube   
https://kubernetes.io/docs/tasks/access-application-cluster/ingress-minikube/

  **error**: unable to recognize "d.yaml": no matches for kind "Ingress" in version "networking.k8s.io/v1"  
   > networking.k8s.io/v1beta1 == 1.14 to 1.18  
   > networking.k8s.io/v1 = 1.19+

#### Commands to run 

    minikube addons enable ingress   
    kubectl get pods -n kube-system   // to verify the ingress controller
    kubectl apply -f ingress_kub_dashboard.yaml
    kubectl get ingresses -n kubernetes-dashboard  or kubectl get ingress -n kubernetes-dashboard  
    vi /etc/hosts  //add ip_address dashboard.com 
    curl dashboard.com  
    kubectl describe ingress dashboard-ingress -n kubernetes-dashboard  
