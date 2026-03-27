## Commandes (payment-service)

# Se placer dans le microservice
cd server/payment-service

# Build de l'image Docker
docker build -t payment-service:latest .

# Chargement de l'image dans kind
kind load docker-image payment-service:latest --name ecommerce-project

# Déploiement du service payment
kubectl apply -f k8s/payment-configmap.yaml
kubectl apply -f k8s/payment-deployment.yaml
kubectl apply -f k8s/payment-service.yaml

# Result
# configmap/payment-configmap created
# deployment.apps/payment-deployment created
# service/payment-service created


# Vérification des ressources
kubectl get all -n ecommerce-project

# Consultation des logs
kubectl logs -n ecommerce-project deployment/payment-deployment
