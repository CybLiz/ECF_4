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

COPY --from=builder /app/target/payment-service.jar app.jar

EXPOSE 9050

ENTRYPOINT ["java", "-jar", "app.jar"]