## Vérification globale du cluster

# Afficher tous les pods du namespace
kubectl get pods -n ecommerce-project

# Result

NAME                                      READY   STATUS    RESTARTS   AGE
auth-deployment-9d494494d-ldhnx           1/1     Running   0          2m47s
client-deployment-5d77d8c459-qmwpx        1/1     Running   0          48m
common-data-deployment-65c5bb49cf-c7cdr   1/1     Running   0          2m44s
mysql-deployment-6748bbf954-n4skj         1/1     Running   0          12m
payment-deployment-64965dc647-qpktx       1/1     Running   0          80m

# Afficher tous les services du namespace
kubectl get services -n ecommerce-project

# Result
NAME                  TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)          AGE
auth-service          ClusterIP   10.xx.xx.x     <none>        7000/TCP         120m
client-service        NodePort    10.xx.xx.xx     <none>        3000:30080/TCP   49m
common-data-service   ClusterIP   10.xx.xxx.x     <none>        9000/TCP         96m
mysql-service         ClusterIP   10.xx.xxx.xxx   <none>        3306/TCP         13m
payment-service       ClusterIP   10.xx.xxx.xxx   <none>        9050/TCP         81m


# Afficher tous les deployments du namespace
kubectl get deployments -n ecommerce-project

# Result
NAME                     READY   UP-TO-DATE   AVAILABLE   AGE
auth-deployment          1/1     1            1           122m
client-deployment        1/1     1            1           51m
common-data-deployment   1/1     1            1           98m
mysql-deployment         1/1     1            1           14m
payment-deployment       1/1     1            1           82m


# Afficher toutes les ressources du namespace
kubectl get all -n ecommerce-project
