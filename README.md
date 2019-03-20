# Use Cases

- Express the relationships among system components
  - Messages: Send, Receive
  - Data: Store, Retrieve
  - Code: Import
  - Actors: Instantiation, Lifetime

# Diagrams

- Sequence diagrams
- Component diagrams

# Design

We can start with the following types of construct:
- Use Cases
- Roles
  For each role we may be interested in modeling/measuring some characteristics.
  - Instances (Actors)
    For each instance (actor),
    - Uptime
    - Number of messages sent & received
      - To/from what roles
      - To/from what actors
      - For what use cases
      - Observed latency for responses to other actors
      - Observed latency for responses from other actors
- Data flow from one component to another, a.k.a. "Message"
  For each message we may be interested in modeling/measuring some characteristics.
  - Health? Quantity, size, frequency (rate), time since last occurrence;
  - Purpose? Qualitative description; Semantic content; Link to use case
  - Protocol?

From this we can derive information--
  - Roles
    - With which other roles do they interact?
      - What is the health of these interactions?
    - In which uses cases do they participate?
  - Use Cases
    - Which roles are involved in each use case?
    - Which messages are involved in each use case?
    - What is the health of the actors and messages involved?


