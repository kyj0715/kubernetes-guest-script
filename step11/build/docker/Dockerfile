FROM eclipse-temurin:21-jre
WORKDIR /app

RUN apt-get update && apt-get install -y dnsutils && rm -rf /var/lib/apt/lists/*

COPY ./app.jar /app/app.jar

# 기본값(필요하면 런타임에 덮어씀)
ENV SPRING_PROFILES_ACTIVE=mysql-dev-group
EXPOSE 8080

ENTRYPOINT ["sh","-c","java -Dspring.profiles.active=${SPRING_PROFILES_ACTIVE} -jar /app/app.jar"]


