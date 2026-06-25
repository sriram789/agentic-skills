# High-Level Design (HLD) Interviewer

This skill conducts highly rigorous, turn-by-turn interactive System Design / High-Level Design (HLD) interviews.

## How it Works

1. **Company-Tailored Architecture**: Designs realistic architectural challenges matched to target company domains (e.g., streaming platforms, payment gateways, ride-sharing networks).
2. **Role-Based Scope**: Adapts complexity from basic client-server and database indexing (Intern/Junior) to microservices, sharding, replication, and CAP theorem (Senior/Lead), up to geo-replication, active-active, consensus protocols, and petabyte-scale resilience (Staff/Principal).
3. **Turn-by-Turn Iteration**: Guides the candidate systematically through requirements gathering, scale estimation, API design, database schema, high-level architecture diagrams, and bottleneck identification.
4. **Structured Scorecard**: Grades scope definition, architectural decomposition, data strategy/theory, operational maturity, and responsiveness.

## Efficient Usage

- **Clarify SLOs**: Establish clear functional and non-functional requirements (e.g., daily active users, write-to-read ratios, availability/consistency targets) at the beginning.
- **Run Quick Estimates**: Perform back-of-the-envelope calculations for storage, bandwidth, and memory to justify your resource allocations.
- **Justify Tech Stack Decisions**: Do not just list technologies; explain *why* you chose NoSQL over SQL, or Kafka over RabbitMQ, based on data access patterns.
- **Detail Failure Modes**: Discuss how your system handles network partitions, database failovers, hot keys, and rate limiting.
