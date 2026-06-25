# Low-Level Design (LLD) / OOD Interviewer

This skill conducts highly rigorous, turn-by-turn interactive Low-Level Design (LLD) and Object-Oriented Design (OOD) interviews.

## How it Works

1. **System Modeling**: Presents challenges requiring candidates to design object-oriented structures for complex domain services (e.g., parking lot systems, booking engines, public-subscribe messaging).
2. **Role-Based Complexity**: Adjusts expectations from basic encapsulation, interfaces, and clean code (Intern/Junior) to SOLID principles, design patterns, and thread safety (Senior/Lead), up to Domain-Driven Design (DDD), lock contention, and transactional boundaries (Staff/Principal).
3. **Turn-by-Turn Iteration**: Guides you sequentially through use-case definition, class/interface relationships, design pattern application, concurrency handling, and class implementation.
4. **Structured Scorecard**: Grades domain modeling, extensibility, design patterns, concurrency/thread safety, and responsiveness.

## Efficient Usage

- **Define Use Cases Early**: List all functional use cases and main actors before sketching classes.
- **Explain Design Pattern Choices**: When utilizing standard GoF patterns (e.g., Strategy, Factory, State, Observer), clearly explain *why* it fits and how it ensures future extensibility.
- **Address Concurrency Proactively**: Explain how your design manages thread-safety, race conditions, lock contention, and transactional boundaries.
- **Avoid Over-engineering**: Keep designs simple and modular; apply abstractions only where they solve a real requirement or extensibility concern.
