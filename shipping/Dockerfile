FROM maven:3.9.14

WORKDIR /app

COPY pom.xml .
COPY src ./src

RUN mvn clean package

EXPOSE 8080

ENV CART_ENDPOINT=cart:8080 \
    DB_HOST=mysql

CMD ["sh", "-c", "java -jar target/*.jar"]