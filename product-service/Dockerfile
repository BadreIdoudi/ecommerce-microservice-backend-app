
FROM openjdk:11
ARG PROJECT_VERSION=0.1.0
RUN mkdir -p /home/app
WORKDIR /home/app
ENV SPRING_PROFILES_ACTIVE dev
ENV SPRING_ZIPKIN_BASE_URL zipkin-container
ENV SPRING_CONFIG_IMPORT cloud-config-container
ENV EUREKA_CLIENT_SERVICE_URL_DEFAULTZONE service-discovery-container
ENV EUREKA_INSTANCE service-discovery-container
COPY product-service/ .
ADD product-service/target/product-service-v${PROJECT_VERSION}.jar product-service.jar
EXPOSE 8500
ENTRYPOINT ["java", "-Dspring.profiles.active=${SPRING_PROFILES_ACTIVE}", "-jar", "product-service.jar"]


