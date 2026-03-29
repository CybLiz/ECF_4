## Commandes (redis)

# Déploiement redis
kubectl apply -f k8s/redis-deployment.yaml
kubectl apply -f k8s/redis-service.yaml
kubectl apply -f k8s/redis-secret.yaml


# Result
# deployment.apps/redis-deployment created
# service/redos-service created
# secret/redis-secret created

# Vérification
kubectl get pods -n ecommerce-project
kubectl get services -n ecommerce-project

