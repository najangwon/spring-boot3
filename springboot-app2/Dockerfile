# Gradle을 사용하여 애플리케이션 빌드
FROM gradle:7.6.1-jdk17 AS build2
WORKDIR /app
COPY . .
RUN gradle bootJar

# 빌드된 JAR 파일을 실행
FROM eclipse-temurin:17-jre-jammy
WORKDIR /app
COPY --from=build2 /app/build/libs/*.jar app2.jar
ENTRYPOINT ["java", "-jar", "app2.jar"]
