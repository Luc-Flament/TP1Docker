FROM eclipse-temurin:17-jdk-alpine
RUN javac Main.java
FROM postgres:14.1-alpine

ENV POSTGRES_DB=db \
   POSTGRES_USER=usr \
   POSTGRES_PASSWORD=pwd
RUN apk update && apk add openjdk11-jre
# Build Main.java with JDK

# TODO : in next steps (not now)
COPY CreateScheme.sql /docker-entrypoint-initdb.d/
COPY InsertData.sql /docker-entrypoint-initdb.d/
COPY Main.class /docker-entrypoint-initdb.d/

