# Banking Transaction & Payments API

A REST API for core banking operations — accounts, deposits, withdrawals and fund transfers — built with Java and Spring Boot.

> 🚧 Work in progress. See the roadmap below.

## Tech stack

Java 17 · Spring Boot 3 · Spring Data JPA · PostgreSQL (H2 for dev) · Spring Security + JWT · JUnit 5 + Mockito · Swagger/OpenAPI · Docker · GitHub Actions

## Design notes

- **Atomic transfers:** debit and credit run in one `@Transactional` method, so a failed transfer rolls back both sides.
- **Money as `BigDecimal`**, never `double`.
- **Consistent errors** via a global `@RestControllerAdvice`.

## Running locally

```bash
mvn spring-boot:run
```

The app starts on `http://localhost:8080` against an in-memory H2 database.
The H2 console is at `http://localhost:8080/h2-console` (JDBC URL `jdbc:h2:mem:bankingdb`).

To run the tests:

```bash
mvn test
```

## Roadmap

- [x] Project setup
- [ ] Account CRUD
- [ ] Deposits and withdrawals
- [ ] Atomic fund transfers
- [ ] Paginated transaction history
- [ ] Global exception handling
- [ ] Spring Security + JWT
- [ ] Unit and integration tests
- [ ] Swagger docs
- [ ] Docker + GitHub Actions CI
