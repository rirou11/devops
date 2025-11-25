Utilisation d'une image de base Java légère

FROM openjdk:17.0.1-jdk-slim

Métadonnées et environnement

LABEL maintainer="rirou11"
ENV APP_PORT 8089
EXPOSE 8089

Définir le répertoire de travail à l'intérieur du conteneur

WORKDIR /app

Copie du JAR construit par Maven dans le conteneur

Correction du chemin : le fichier JAR se trouve dans 'target/' par rapport au contexte de build (DevOps-main)

COPY target/student-management-0.0.1-SNAPSHOT.jar /app/app.jar

Commande pour démarrer l'application Spring Boot

ENTRYPOINT ["java", "-jar", "app.jar"]
