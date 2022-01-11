### Repository for the K8s in 1 hour video

#### K8s manifest files 
* mongo-config.yaml
* mongo-secret.yaml
* mongo.yaml
* webapp.yaml

#### K8s commands

##### start Minikube and check status
    minikube start --vm-driver=hyperkit (OR) minikube start --driver docker
    minikube status
    Install minikube : brew install minikube
    Start minikube: minikube start --driver docker (or) minikube start --driver=hyperkit
    Check Status: minikube status
    Delete minikube cluster: minikube delete
    Check the k8s cluster running locally: kubectl get node


##### get minikube node's ip address
    minikube ip
    
##### To apply local K8s config files and create service
    kubectl apply -f <yaml_file path>
    kubectl apply -f mongo-secret.yaml

##### get basic info about k8s components
    kubectl get node
    kubectl get pod
    kubectl get svc
    kubectl get all
    kubectl get configmap
    kubectl get secret
    
##### get basic info about k8s components
    To get commands supported: kubectl --help
    TO get command + help summary: kubectl get --help

##### get extended info about components
    kubectl get pod -o wide
    kubectl get node -o wide

##### get detailed info about a specific component
    kubectl describe svc {svc-name}
    kubectl describe pod {pod-name}

##### get application logs
    To check: kubectl logs {pod-name}
    To stream: kubectl logs {pod-name} -f
    
##### stop your Minikube cluster
    minikube stop

<br />

> :warning: **Known issue - Minikube IP not accessible** 

If you can't access the NodePort service webapp with `MinikubeIP:NodePort`, execute the following command:
    
    minikube service webapp-service

<br />

#### Links
* mongodb image on Docker Hub: https://hub.docker.com/_/mongo
* webapp image on Docker Hub: https://hub.docker.com/repository/docker/nanajanashia/k8s-demo-app
* k8s official documentation: https://kubernetes.io/docs/home/
* webapp code repo: https://gitlab.com/nanuchi/developing-with-docker/-/tree/feature/k8s-in-hour
