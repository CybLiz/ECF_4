## Commandes (authentication-service)

# Se placer dans le microservice
cd server/authentication-service

# Build de l'image Docker
docker build -t authentication-service:latest .

# Création du cluster kind
kind create cluster --config kind/basic-cluster.yaml

# Result
# Creating cluster "ecommerce-project" ...
# Set kubectl context to "kind-ecommerce-project"

NAME                              STATUS   ROLES           AGE   VERSION
ecommerce-project-control-plane   Ready    control-plane   34m   v1.35.0
ecommerce-project-worker          Ready    <none>          34m   v1.35.0
ecommerce-project-worker2         Ready    <none>          34m   v1.35.0



# Chargement de l'image dans kind
kind load docker-image authentication-service:latest --name ecommerce-project

# Result
# Image loaded into cluster


# Création du namespace
kubectl apply -f k8s/namespace.yaml

# Result
# namespace/ecommerce-project created


# Déploiement du service d'authentification

kubectl apply -f k8s/auth-configmap.yaml
kubectl apply -f k8s/auth-secret.yaml
kubectl apply -f k8s/auth-deployment.yaml
kubectl apply -f k8s/auth-service.yaml

# Result
# configmap/auth-configmap created
# secret/auth-secret created
# deployment.apps/auth-deployment created
# service/auth-service created


# Vérification des ressources
kubectl get all -n ecommerce-project

# Result

NAME                                   READY   STATUS    RESTARTS      AGE
pod/auth-deployment-7b4cbffb75-snxxl   1/1     Running   1 (12s ago)   40s

#
NAME                   TYPE        CLUSTER-IP    EXTERNAL-IP   PORT(S)    AGE
service/auth-service   ClusterIP   10.xx.xx.x   <none>        7000/TCP   2s

#
NAME                              READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/auth-deployment   1/1     1            1           40s

# Consultation des logs
kubectl logs -n ecommerce-project deployment/auth-deployment

