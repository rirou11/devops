# ==============================================================================
# 1. BUILDER STAGE (Préparation des couches du JAR)
# Ce stage n'est utilisé que pour séparer les dépendances
# ==============================================================================
FROM amazoncorretto:17-alpine AS builder

# Le JAR de Spring Boot a une structure de couches optimisée
ARG JAR_FILE=target/student-management-0.0.1-SNAPSHOT.jar

# Utilise l'outil Spring Boot pour décomposer le JAR en couches distinctes
COPY ${JAR_FILE} app.jar
RUN java -Djarmode=layertools -jar app.jar extract --destination extracted

# ==============================================================================
# 2. FINAL STAGE (Image finale légère et optimisée pour le cache)
# ==============================================================================
FROM amazoncorretto:17-alpine

# Dossier de travail
WORKDIR /app

# Exposer le port de l'application (par défaut pour Spring Boot)
EXPOSE 8080

# 1. Copier les couches qui changent le moins souvent
COPY --from=builder /app/extracted/dependencies/ ./
COPY --from=builder /app/extracted/spring-boot-loader/ ./
COPY --from=builder /app/extracted/snapshot-dependencies/ ./

# 2. Copier la couche d'application (qui change à chaque modification de code)
# Cette étape est la seule qui invalidera le cache après un changement de code
COPY --from=builder /app/extracted/application/ ./

# Lancement de l'application avec la structure de fichiers décomposée
CMD ["java", "org.springframework.boot.loader.JarLauncher"]
