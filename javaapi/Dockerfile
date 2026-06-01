FROM maven:3.9-eclipse-temurin-8 AS builder

WORKDIR /usr/src/app

COPY ./ /usr/src/app/

RUN mvn install -DskipTests

FROM eclipse-temurin:8

WORKDIR /usr/src/app/

COPY --from=builder /usr/src/app/target/book-work-0.0.1-SNAPSHOT.jar ./book-work-0.0.1.jar

EXPOSE 8080

ENTRYPOINT ["java","-jar","book-work-0.0.1.jar"]