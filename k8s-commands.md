# kubectl apply commands in order
    
    kubectl apply -f mongo-secret.yaml
    kubectl apply -f mongo.yaml
    kubectl apply -f mongo-configmap.yaml 
    kubectl apply -f mongo-express.yaml

# kubectl get commands

    kubectl get pod
    kubectl describe pod <podname>
    kubectl get pod --watch
    kubectl get pod -o wide
    kubectl get service
    kubectl describe service <servicename>
    kubectl get secret
    kubectl get all (get all the components)
    kubectl get all | grep mongodb (get all filtered components)
    kubectl logs <podname>

# kubectl debugging commands

    kubectl describe pod mongodb-deployment-
    kubectl describe service mongodb-service
    kubectl logs mongo-express-

# give a URL to external service in minikube

    minikube service mongo-express-service

# ingress commands

    minikube addons enable ingress
    kubectl get pod -n kube-system (which ingress controller is runnung inside your namespace cluster)
    kubectl get ns (clusters)
# In minikube cluster k8 dashboard already exists not accessible externally

    kubectl gett -n kubernetes-dashboard (shows all the component of that daashboard)
    kubectl get ingress -n kubernetes-dashboard (to show ingress we made)
    sudo vim /etc/hosts
    kubectl describe ingress dashboard-ingress -n kubernetes-dashboard
#   multiple path for same hosts
    http://satyam.com/......
#   multiple sub-domain / hosts
    http://paytm.satyam.com
#   configuring TLS Certificate - https://
    use tls : above rules in .yaml incluing secretname
    reference in data :
    data keys must be tls.crt & tls.key
