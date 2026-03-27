### Sujet ECF : Amélioration et extension d'une architecture microservices e-commerce

**Destinataires :** Architectes logiciels

**Objectif :** Cet exercice a pour but d'évaluer votre capacité à analyser une architecture microservices existante, à l'améliorer sur les plans de la qualité, de la résilience et de la maintenabilité, et à l'enrichir par la conception et le développement de nouveaux microservices cohérents avec le domaine métier e-commerce.

#### **Contexte**

Vous avez accès au code source d'une application e-commerce partielle, structurée en microservices Spring Boot avec une interface React. L'architecture actuelle est fonctionnelle mais incomplète et perfectible. En tant qu'architecte logiciel, votre mission est triple : **analyser et critiquer** l'architecture existante, **l'améliorer** en appliquant les bonnes pratiques, et **la compléter** par de nouveaux microservices que vous jugerez pertinents.

#### **Description de l'application existante**

L'application repose sur plusieurs microservices Spring Boot et une interface utilisateur React.

- **Microservice manquant à compléter :**
  - **Service de suggestions de recherche :** Ce service doit être implémenté pour proposer des suggestions de recherche en temps réel.

- **Interface utilisateur (UI) React :** Consomme les API fournies par les microservices.

#### **Instructions**

1. **Analyse critique de l'architecture existante :**
   - Analysez le code source fourni et produisez un **document d'architecture** (ADR ou diagramme C4) décrivant l'état actuel.
   - Identifiez les points faibles : couplage fort, absence de tolérance aux pannes, manque d'observabilité, lacunes de sécurité, etc.
   - Proposez et justifiez les améliorations à apporter.


2. **Développement du microservice de recherche (manquant) :**
   - Développez le service de suggestions de recherche avec Spring Boot.
   - Assurez sa bonne intégration avec les autres services et l'UI.


## Obligatoire
4. **Dockerisation et orchestration :**
   - Créez un `Dockerfile` optimisé pour chaque microservice (multi-stage build recommandé).
   - Dockerisez l'interface utilisateur React.
   - Rédigez les manifests kubernetes.

5. **Documentation :**
   - Documentez l'architecture cible avec un diagramme (C4, UML ou équivalent).
   - Fournissez les instructions de build et de démarrage de l'ensemble de l'application.
   - Décrivez les choix techniques et architecturaux effectués, et les compromis associés.

#### **Livrables**

- Document d'architecture (état actuel + cible) avec justification des choix.
- `Dockerfile` pour chaque microservice et pour l'interface utilisateur.
- manifests Kubernetes pour l'orchestration complète.
- Code source du microservice de recherche.
- Documentation de déploiement et guide de test.
