## Vérification globale du cluster

# Afficher tous les pods du namespace
kubectl get pods -n ecommerce-project

# Result

NAME                                      READY   STATUS    RESTARTS   AGE

auth-deployment-9d494494d-ldhnx           1/1     Running   0          2d6h
client-deployment-77d677444c-lds8j        1/1     Running   0          2d2h
common-data-deployment-65c5bb49cf-c7cdr   1/1     Running   0          2d6h
mysql-deployment-6748bbf954-n4skj         1/1     Running   0          2d6h
payment-deployment-64965dc647-qpktx       1/1     Running   0          2d7h
redis-deployment-7b47bcd464-d9lxc         1/1     Running   0          2d2h


# Afficher tous les services du namespace
kubectl get services -n ecommerce-project

# Result
NAME                  TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)          AGE

auth-service          ClusterIP   10.xx.xx.x     <none>        7000/TCP       2d8h
client-service        NodePort    10.xx.xx.xx     <none>        80:30080/TCP   2d7h
common-data-service   ClusterIP   10.xx.xxx.x     <none>        9000/TCP       2d7h
mysql-service         ClusterIP   10.xx.xxx.xxx   <none>        3306/TCP       2d6h
payment-service       ClusterIP   10.xx.xxx.xxx    <none>        9050/TCP       2d7h
redis-service         ClusterIP   10.xx.xxx.xxx    <none>        6379/TCP       2d2h



# Afficher tous les deployments du namespace
kubectl get deployments -n ecommerce-project

# Result
NAME                     READY   UP-TO-DATE   AVAILABLE   AGE

auth-deployment          1/1     1            1           2d8h
client-deployment        1/1     1            1           2d7h
common-data-deployment   1/1     1            1           2d8h
mysql-deployment         1/1     1            1           2d6h
payment-deployment       1/1     1            1           2d7h
redis-deployment         1/1     1            1           2d2h



# Afficher toutes les ressources du namespace
kubectl get all -n ecommerce-project

