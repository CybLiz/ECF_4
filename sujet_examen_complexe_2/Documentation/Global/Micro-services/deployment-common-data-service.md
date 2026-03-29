## Commandes (common-data-service)

# Se placer dans le microservice
cd server/common-data-service

# Build de l'image Docker
docker build -t common-data-service:latest .

# Chargement de l'image dans kind
kind load docker-image common-data-service:latest --name ecommerce-project

# Déploiement du service common-data
kubectl apply -f k8s/common-data-configmap.yaml
kubectl apply -f k8s/common-data-secret.yaml
kubectl apply -f k8s/common-data-deployment.yaml
kubectl apply -f k8s/common-data-service.yaml

# Result
# configmap/common-data-configmap created
# secret/common-data-secret created
# deployment.apps/common-data-deployment created
# service/common-data-service created


# Vérification des ressources
kubectl get all -n ecommerce-project

# Consultation des logs
kubectl logs -n ecommerce-project deployment/common-data-deployment

