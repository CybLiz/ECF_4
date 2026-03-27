## Commandes (mysql)

# Déploiement MySQL
kubectl apply -f k8s/mysql-secret.yaml
kubectl apply -f k8s/mysql-pvc.yaml
kubectl apply -f k8s/mysql-deployment.yaml
kubectl apply -f k8s/mysql-service.yaml

# Result
# secret/mysql-secret created
# persistentvolumeclaim/mysql-pvc created
# deployment.apps/mysql-deployment created
# service/mysql-service created


# Vérification
kubectl get pods -n ecommerce-project

kubectl get services -n ecommerce-project

