# Dockerfile Simple et stable
FROM amazoncorretto:17-alpine

WORKDIR /app

# Copier le JAR généré par Maven
COPY target/student-management-0.0.1-SNAPSHOT.jar app.jar

# Lancement de l'application
CMD ["java", "-jar", "app.jar"]
