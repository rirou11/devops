# IMAGE DE BASE LÉGÈRE
FROM amazoncorretto:17-alpine

# Dossier de travail
WORKDIR /app

# Exposer le port Spring Boot
EXPOSE 8080

# Copier le JAR généré
COPY target/student-management-0.0.1-SNAPSHOT.jar app.jar

# Lancement de l'application
CMD ["java", "-jar", "app.jar"]
