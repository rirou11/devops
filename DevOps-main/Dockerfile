# Utilisation de l'image de base OpenJDK 17 (version slim pour la taille)
FROM openjdk:17.0.1-jdk-slim

# Définition du répertoire de travail à l'intérieur du conteneur
WORKDIR /app

# Copie du JAR construit par Maven dans le conteneur
# Le JAR est dans target/ et a ce nom : student-management-0.0.1-SNAPSHOT.jar
COPY DevOps-main/target/student-management-0.0.1-SNAPSHOT.jar /app/app.jar

# Exposition du port par défaut de l'application Spring Boot (si c'est 8080 ou 8089)
EXPOSE 8089

# Commande pour exécuter l'application
ENTRYPOINT ["java", "-jar", "/app/app.jar"]
