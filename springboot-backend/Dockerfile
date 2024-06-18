FROM maven:3.9.7-eclipse-temurin-17-alpine as builder

WORKDIR /app

COPY . .


RUN mvn -DskipTests compile

RUN mvn -DskipTests package

FROM openjdk:17

#EXPOSE 8080

#RUN mkdir -p /app

WORKDIR /app

COPY --from=builder /app/target/springboot-backend-*.jar /app/springboot-backend.jar


ENTRYPOINT ["java","-jar" ,"/app/springboot-backend.jar"]

