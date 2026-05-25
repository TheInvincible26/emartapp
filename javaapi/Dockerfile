FROM openjdk:latest AS builder
WORKDIR /usr/src/app
RUN apt update && apt install maven -y
COPY ./ /usr/src/app/
RUN mvn install -DskipTests


FROM openjdk:latest 
WORKDIR /usr/src/app/
COPY --from=builder /usr/src/app/target/book-work-0.0.1-SNAPSHOT.jar ./book-work-0.0.1.jar

EXPOSE 8080

ENTRYPOINT [ "java", "-jar", "book-work-0.0.1.jar" ]
