FROM maven:3.9.14

EXPOSE 8080

WORKDIR /app

COPY pom.xml .

COPY src .

RUN muv clean package

ENV CART_ENDPOINT="cart:8080" \
    DB_HOST="mysql" \

CMD ["java", "-jar", "shipping.jar"]