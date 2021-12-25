
FROM openjdk:11
ARG PROJECT_VERSION=0.1.0
RUN mkdir -p /home/app
WORKDIR /home/app
ENV SPRING_PROFILES_ACTIVE dev
ENV SPRING_ZIPKIN_BASE_URL zipkin-container
ENV SPRING_CONFIG_IMPORT cloud-config-container
ENV EUREKA_CLIENT_SERVICE_URL_DEFAULTZONE service-discovery-container
ENV EUREKA_INSTANCE service-discovery-container
COPY payment-service/ .
ADD payment-service/target/payment-service-v${PROJECT_VERSION}.jar payment-service.jar
EXPOSE 8400
ENTRYPOINT ["java", "-Dspring.profiles.active=${SPRING_PROFILES_ACTIVE}", "-jar", "payment-service.jar"]


