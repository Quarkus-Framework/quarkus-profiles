# quarkus-profiles

This project uses Quarkus, the Supersonic Subatomic Java Framework.

If you want to learn more about Quarkus, please visit its website: https://quarkus.io/ .

## Context
CRUD application with Quarkus and library Panache, that shows like to have multiple configurations per profile
in the same `application.properties` file.

- In this app we used Hibernate ORM with Panache.

- For Packaging the application, digit: mvn clean compile package 
  - After this, running in PROD mode the application digiting: 
    java -jar target/quarkus-profiles-1.0.0-SNAPSHOT-runner.jar
    Trying to call `http://localhost:8080/hello` will be return the right response
  - After this, running in DEV mode the application digiting:
    java -Dquarkus.profile=dev -jar target/quarkus-profiles-1.0.0-SNAPSHOT-runner.jar
    Trying to call `http://localhost:8082/hello` will be return the right response
  - After this, running in TEST mode the application digiting:
    java -Dquarkus.profile=test -jar target/quarkus-profiles-1.0.0-SNAPSHOT-runner.jar
    Trying to call `http://localhost:9090/hello` will be return the right response  
 

## Tecnologies used
Extension:
- RestEasy: to write reactive rest service.
- RESTEasy Jackson: help to write rest service.
- Config-yaml: library to support write file.yml
- JDBC-H2: we use H2 inline database for testing.
- JDBC-Postgres: we use Postgres as DB.
- Quarkus Hibernate Panache: Hibernate ORM with Panache library.
- Junit5, Rest-Assured: integration and unit tests

## Running the application in dev mode

You can run your application in dev mode that enables live coding using:
```shell script
./mvnw compile quarkus:dev
```

> **_NOTE:_**  Quarkus now ships with a Dev UI, which is available in dev mode only at http://localhost:8080/q/dev/.

## Packaging and running the application

The application can be packaged using:
```shell script
./mvnw package
```
It produces the `quarkus-run.jar` file in the `target/quarkus-app/` directory.
Be aware that it’s not an _über-jar_ as the dependencies are copied into the `target/quarkus-app/lib/` directory.

The application is now runnable using `java -jar target/quarkus-app/quarkus-run.jar`.

If you want to build an _über-jar_, execute the following command:
```shell script
./mvnw package -Dquarkus.package.type=uber-jar
```

The application, packaged as an _über-jar_, is now runnable using `java -jar target/*-runner.jar`.

## Creating a native executable

You can create a native executable using: 
```shell script
./mvnw package -Pnative
```

Or, if you don't have GraalVM installed, you can run the native executable build in a container using: 
```shell script
./mvnw package -Pnative -Dquarkus.native.container-build=true
```

You can then execute your native executable with: `./target/quarkus-profiles-1.0.0-SNAPSHOT-runner`

If you want to learn more about building native executables, please consult https://quarkus.io/guides/maven-tooling.

## Related Guides

- JDBC Driver - H2 ([guide](https://quarkus.io/guides/datasource)): Connect to the H2 database via JDBC
- RESTEasy Classic ([guide](https://quarkus.io/guides/resteasy)): REST endpoint framework implementing JAX-RS and more
- Hibernate ORM with Panache ([guide](https://quarkus.io/guides/hibernate-orm-panache)): Simplify your persistence code for Hibernate ORM via the active record or the repository pattern
- Agroal - Database connection pool ([guide](https://quarkus.io/guides/datasource)): Pool JDBC database connections (included in Hibernate ORM)
- JDBC Driver - PostgreSQL ([guide](https://quarkus.io/guides/datasource)): Connect to the PostgreSQL database via JDBC

## Provided Code

### Hibernate ORM

Create your first JPA entity

[Related guide section...](https://quarkus.io/guides/hibernate-orm)

[Related Hibernate with Panache section...](https://quarkus.io/guides/hibernate-orm-panache)


### RESTEasy JAX-RS

Easily start your RESTful Web Services

[Related guide section...](https://quarkus.io/guides/getting-started#the-jax-rs-resources)
