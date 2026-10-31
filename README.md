# Akshit Khandelwal

Backend engineer working in Java/Spring Boot and Python/FastAPI on PostgreSQL. Currently at
Volkswagen Group Digital Solutions, where I took a multi-tenant vulnerability-management platform
from proof of concept to production for three enterprise clients and 120+ monitored servers, and
now also work on a multi-tenant RAG assistant.

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

**[Confide](https://confide.life)** is a mental-health support app I build, live on
[Google Play](https://play.google.com/store/apps/details?id=com.confide.app) in India. FastAPI,
PostgreSQL with pgvector and Claude behind an Expo app. The code is private; the parts worth
talking about:

- A 49-scenario eval harness that runs the real prompt pipeline and grades replies against safety
  rules, because unit tests with a mocked model cannot see a rule stop being followed. Comparing
  runs showed that moving a rule higher in the prompt halved violations, where rewording it did
  nothing.
- Health data treated as the thing the product exists to protect: analytics carry counts, never
  content, and a test fails the build if an exception message could reach the logs.
- Most of the code is written with Claude Code, under checked-in repo rules and a review pass on
  every pull request.

### Stack

Java · Spring Boot · Python · FastAPI · PostgreSQL · pgvector · Claude API · Docker · AWS ·
Flyway · Testcontainers

### Elsewhere

[Portfolio](https://akshit-khandelwal47.github.io/portfolio/) ·
[LinkedIn](https://linkedin.com/in/akshit-khandelwal20) ·
[Email](mailto:akshitkhandelwal20@gmail.com)
