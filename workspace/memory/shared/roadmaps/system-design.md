# System Design Roadmap (from roadmap.sh)

## 1. Key Concepts
- Performance vs Scalability, Latency vs Throughput
- Availability vs Consistency, CAP Theorem (AP, CP)

## 2. Consistency Patterns
- Weak Consistency, Eventual Consistency, Strong Consistency

## 3. Availability Patterns
- Fail-Over (Active-Active, Active-Passive)
- Replication (Master-Slave, Master-Master)
- Availability in Numbers (99.9%, 99.99%)

## 4. Asynchronism
- Background Jobs, Event-Driven, Schedule Driven

## 5. Infrastructure & Networking
### DNS & CDN
- Domain Name System, CDNs (Push, Pull)
### Load Balancing
- LB vs Reverse Proxy, Layer 4 vs Layer 7, Algorithms
### Scaling
- Horizontal Scaling, Microservices, Service Discovery

## 6. Data Management
### Database Fundamentals
- SQL vs NoSQL
### Scaling Techniques
- Sharding, Federation, Denormalization, SQL Tuning
### Database Types
- RDBMS, Key-Value Store, Document Store, Wide Column Store, Graph DBs

## 7. Caching
### Strategies
- Refresh Ahead, Write-Behind, Write-Through, Cache Aside
### Levels
- Client, CDN, Web Server, Database, Application

## 8. Message Queues
- Back Pressure, Task Queues, Message Queues

## 9. Communication Protocols
- HTTP, TCP, UDP, RPC, REST, gRPC, GraphQL

## 10. Performance Antipatterns
- Busy Database, Busy Frontend, Chatty I/O, Extraneous Fetching
- Improper Instantiation, Monolithic Persistence, No Caching
- Noisy Neighbor, Retry Storm, Synchronous I/O

## 11. Monitoring & Observability
- Health, Availability, Performance, Security, Usage Monitoring
- Instrumentation, Visualization & Alerts

## 12. Cloud Design Patterns
### Messaging
- Publisher/Subscriber, Priority Queue, Competing Consumers, Choreography
### Data Management
- Event Sourcing, CQRS, Cache-Aside, Sharding, Materialized View
### Design & Implementation
- Strangler Fig, Sidecar, Gateway (Routing/Offloading/Aggregation)
- Leader Election, Backends for Frontend, Anti-Corruption Layer
### Reliability
- Bulkhead, Throttling, Health Endpoint Monitoring, Deployment Stamps

*Source: roadmap.sh/system-design — fetched 2026-04-05*
