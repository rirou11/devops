# IMAGE DE BASE LÉGÈRE
FROM amazoncorretto:17-alpine

# Dossier de travail
WORKDIR /app

# Exposer le port par défaut de Spring Boot
EXPOSE 8080

# Copier le JAR généré par Maven
COPY target/student-management-0.0.1-SNAPSHOT.jar app.jar

# Lancer l'application
CMD ["java", "-jar", "app.jar"]
