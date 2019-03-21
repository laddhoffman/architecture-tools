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

# Considerations

- When each actor initializes
  - Actor should generate a new unique ID
  - Actor should report its ID and Role
- When an actor sends a message
  - Actor should assign the message a unique ID
  - Is the message a followup from a preceding message (or other event)?
    - If so, actor should include the transaction ID of the preceding message
    - Otherwise, actor should assign the message a new transaction ID
  - Actor should report the following:
    - Actor ID
    - Role
    - Message ID
    - Use case ID
    - Transacion ID
    - Routing Mechanism
    - Routing Key
    - Timestamp
    - Message Type
    - Message Properties (Optional)
- When an actor receives a message
  - Actor should report the following:
    - Source
    - Transmission Pathway
    - Actor ID
    - Role
    - Message ID
    - Message Type
    - Message Properties (Optional)
    - Timestamp
- When an actor stores data
  - Actor should report the following
    - Actor ID
    - Role
    - Data Type
    - Data Properties (Optional)
    - Timestamp

Routing Mechanism may be one of the following:
  - Direct
  - Topic
  - Fan-out

Routing Key will depend on the routing mechanism.

# Questions

Should we attempt to model/measure data storage/retrieval and message routing
components themselves? Or is it sufficient or preferable to exclude these and
only model the actors?
