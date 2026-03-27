# Authentication Service

## Description

Le `authentication-service` est un microservice Spring Boot chargé de gérer l’authentification des utilisateurs dans l’application e-commerce.

---

## Dockerisation

### Création du Dockerfile

Le microservice est conteneurisé à l’aide d’un Dockerfile multi-stage afin d’optimiser la taille de l’image finale.

```Dockerfile
# Stage 1 : Build
FROM maven:3.8.6-eclipse-temurin-11 AS builder

WORKDIR /app

COPY pom.xml .
RUN mvn dependency:go-offline -B

COPY src ./src

RUN mvn clean package -DskipTests

# Stage 2 : Runtime
FROM eclipse-temurin:11-jre-alpine

WORKDIR /app

RUN addgroup -S appgroup && adduser -S appuser -G appgroup
USER appuser

COPY --from=builder /app/target/authentication-service.jar app.jar

EXPOSE 7000

ENTRYPOINT ["java", "-jar", "app.jar"]
```