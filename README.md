# Akshit Khandelwal

Backend engineer working in Java, Spring Boot and PostgreSQL. Currently at Volkswagen Group
Digital Solutions, where I took a multi-tenant vulnerability-management platform from proof of
concept to production for three enterprise clients and 120+ monitored servers.

What interests me most is the part of a system that decides what happens when something fails:
retries that don't duplicate, races that don't lose writes, failure states you can query instead
of guess at.

### What I'm building

**[escalade](https://github.com/akshit-khandelwal47/escalade)** is a self-hostable on-call and
escalation engine, built around four delivery guarantees rather than CRUD over a notifications
table:

- Idempotent incident creation, enforced by a partial unique index rather than a racy pre-check
- `SELECT … FOR UPDATE SKIP LOCKED` job claiming, so several workers cooperate with no broker
- An optimistic lock that closes the acknowledge-versus-escalate race
- Retry, backoff and dead-lettering, so a failed channel surfaces instead of silently swallowing
  a page

Spring Boot 3, Java 21, Postgres, Flyway, Testcontainers, CI on GitHub Actions.

**[Write-ups](https://akshit-khandelwal47.github.io/portfolio/)** on the design decisions above,
including why I did not reach for a message broker and what would make me change that.

### Stack

Java · Spring Boot · Python · FastAPI · PostgreSQL · Docker · AWS · Flyway · Testcontainers

### Elsewhere

[Portfolio](https://akshit-khandelwal47.github.io/portfolio/) ·
[LinkedIn](https://linkedin.com/in/akshit-khandelwal20) ·
[Email](mailto:akshitkhandelwal20@gmail.com)
