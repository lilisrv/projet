# Utiliser une image Maven officielle avec Eclipse Temurin JDK 17 comme image de base
FROM maven:3.9.9-eclipse-temurin-17 AS build

# Définir le répertoire de travail
WORKDIR /app

# Copier le fichier pom.xml
COPY app/pom.xml .

# Copier le dossier src
COPY app/src ./src

# Compiler le projet
RUN mvn clean package

# Utiliser une image OpenJDK officielle comme image de base pour exécuter l'application
FROM openjdk:17-jdk-slim

# Définir le répertoire de travail
WORKDIR /app

# Copier les artefacts construits à partir de l'étape de construction
COPY --from=build /app/target/demo-0.0.1.jar /app/demo-0.0.1.jar

# Définir la commande par défaut pour exécuter l'application
CMD ["java", "-jar", "/app/demo-0.0.1.jar"]

