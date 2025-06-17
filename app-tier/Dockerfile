# Base image with Amazon Corretto JDK
FROM public.ecr.aws/amazoncorretto/amazoncorretto:17

# Install MySQL client (no sudo)
RUN yum update -y && \
    yum install -y mysql && \
    yum clean all

# Set working directory
WORKDIR /app

# Copy the built JAR
COPY target/*.jar app.jar

# Expose default port
EXPOSE 80

# Run the app
ENTRYPOINT ["java", "-jar", "app.jar"]
