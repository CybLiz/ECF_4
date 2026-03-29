## Commandes (client)

# Se placer dans le dossier client
cd client

# Build de l'image Docker
docker build -t ecommerce-client:latest .

# Chargement de l'image dans kind
kind load docker-image ecommerce-client:latest --name ecommerce-project

# Déploiement du client
kubectl apply -f k8s/client-configmap.yaml
kubectl apply -f k8s/client-deployment.yaml
kubectl apply -f k8s/client-service.yaml

# Result
# configmap/client-configmap created
# deployment.apps/client-deployment created
# service/client-service created


# Vérification des ressources
kubectl get all -n ecommerce-project

# Consultation des logs
kubectl logs -n ecommerce-project deployment/client-deployment
