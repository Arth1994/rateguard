# RateGuard

A distributed rate-limiting microservice for enforcing fair, configurable request limits on APIs and external-facing services.

## What it does

RateGuard sits in front of a service and enforces rate limits on incoming requests, so a single client can't crowd out everyone else or abuse an endpoint.

- **Multiple rate-limiting algorithms** — modular design, so the limiting strategy can be swapped per use case
- **Dynamic configuration** — limits can be adjusted without redeploying
- **Redis-backed caching** — limit state is kept in Redis for fast checks and shared state across instances
- **Authentication and authorization** — secured endpoints for managing limits
- **Monitoring and metrics** — visibility into limiting activity

## Tech stack

- Java / Spring Boot
- Redis
- REST APIs

## Getting started

Prerequisites: JDK 8 or later, a Spring Boot development environment, and a Redis server.

```shell
git clone https://github.com/Arth1994/rateguard.git
cd rateguard
```

Configure your Redis connection and rate-limit rules, then build and run with Maven or Gradle as a standard Spring Boot application.

## Why I built it

Rate limiting is one of those problems that looks trivial until it has to work across instances under real traffic. This project is my exploration of the design trade-offs: algorithm choice, shared state in Redis, and keeping the check fast enough to sit on the request path.

## License

MIT
