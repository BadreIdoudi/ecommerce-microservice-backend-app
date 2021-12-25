
FROM openjdk:11
ARG PROJECT_VERSION=0.1.0
RUN mkdir -p /home/app
WORKDIR /home/app
ENV SPRING_ZIPKIN_BASE_URL zipkin-container
ENV SPRING_CONFIG_IMPORT cloud-config-container
ENV EUREKA_CLIENT_SERVICE_URL_DEFAULTZONE service-discovery-container
ENV EUREKA_INSTANCE service-discovery-container
COPY cloud-config/ .
ADD cloud-config/target/cloud-config-v${PROJECT_VERSION}.jar cloud-config.jar
EXPOSE 9296
ENTRYPOINT ["java", "-jar", "cloud-config.jar"]


