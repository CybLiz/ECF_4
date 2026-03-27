# Build et démarrage de l'application

## Stack

- Java 11
- Maven 3.8+
- Node.js / Yarn
- Docker
- kind
- kubectl

## Structure du projet

- `client` : interface React
- `server/authentication-service` : microservice d’authentification
- `server/common-data-service` : microservice de données communes
- `server/payment-service` : microservice de paiement
- `k8s` : manifests Kubernetes
- `kind` : configuration du cluster local

## Build des images Docker

Services :

```bash
docker build -t authentication-service:latest .
docker build -t ecommerce-client:latest .
docker build -t common-data-service:latest .
docker build -t payment-service:latest .
```

