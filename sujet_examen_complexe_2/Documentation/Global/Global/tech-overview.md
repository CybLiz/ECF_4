## Choix techniques et architecturaux

### Dockerisation

Chaque microservice a été conteneurisé avec une approche multi-stage :

- **Spring Boot services (auth, common-data, payment)** :
  - Build avec Maven
  - Runtime léger avec OpenJDK (eclipse-temurin)
- **Frontend React** :
  - Build avec Node.js 14
  - Runtime avec NGINX pour servir les fichiers statiques

### Orchestration Kubernetes

L’application est déployée sur un cluster local `kind`.

Pour chaque service :
- un **Deployment** pour la gestion des pods
- un **Service** pour l’exposition interne (ClusterIP)
- un **NodePort** pour le frontend

### Configuration

- Utilisation de **ConfigMap** pour les variables non sensibles
- Utilisation de **Secret** pour les mots de passe (MySQL, Redis)
- Séparation de la configuration par microservice pour réduire le couplage

### Base de données

- Déploiement de **MySQL** dans Kubernetes
- Utilisation d’un **PersistentVolumeClaim** pour assurer la persistance des données

### Reverse proxy frontend

Le frontend est servi par **NGINX** avec un reverse proxy :

- `/api/auth/` → `auth-service`
- `/api/data/` → `common-data-service`
- `/api/payment/` → `payment-service`

Cela permet :
- de centraliser les appels API
- d’éviter les problèmes CORS
- de simplifier les URLs côté frontend

---