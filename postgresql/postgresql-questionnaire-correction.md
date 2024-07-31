# Correction du Questionnaire sur PostgreSQL

## Questions à choix unique (en français)

1. Quel type de base de données est PostgreSQL ?
   
   Réponse correcte : a) Relationnelle
   
   Explication : PostgreSQL est principalement une base de données relationnelle, bien qu'elle prenne également en charge certaines fonctionnalités NoSQL comme le stockage et la recherche de données JSON.

2. Quelle commande SQL est utilisée pour créer un nouvel index dans PostgreSQL ?
   
   Réponse correcte : d) CREATE INDEX
   
   Explication : La commande SQL standard pour créer un nouvel index dans PostgreSQL est CREATE INDEX. Par exemple : CREATE INDEX idx_name ON table_name (column_name);

## Questions ouvertes (en anglais)

1. Explain the ACID properties in the context of PostgreSQL. Why are they important for database transactions?

   Réponse modèle : 
   ACID stands for Atomicity, Consistency, Isolation, and Durability. In PostgreSQL:

   Atomicity: Ensures that a transaction is treated as a single, indivisible unit. Either all operations in a transaction are completed successfully, or none of them are.

   Consistency: Guarantees that a transaction brings the database from one valid state to another. All data written to the database must be valid according to all defined rules.

   Isolation: Ensures that concurrent execution of transactions leaves the database in the same state that would have been obtained if the transactions were executed sequentially.

   Durability: Once a transaction has been committed, it will remain committed even in the case of a system failure.

   Importance:
   1. Data Integrity: ACID properties ensure that data remains accurate and consistent.
   2. Reliability: Transactions are protected against system failures.
   3. Concurrency: Multiple users can work with the database simultaneously without corrupting data.
   4. Predictability: Developers can rely on consistent behavior when designing applications.

   PostgreSQL's strong ACID compliance makes it suitable for applications where data integrity and reliability are crucial, such as financial systems or mission-critical business applications.

2. What is the difference between a View and a Materialized View in PostgreSQL? When would you use one over the other?

   Réponse modèle:
   Views and Materialized Views in PostgreSQL are both virtual tables based on a query, but they have important differences:

   View:
   - A stored query that dynamically retrieves data when accessed.
   - Always returns up-to-date data.
   - Does not store data physically.
   - Useful for simplifying complex queries or restricting access to data.

   Materialized View:
   - Stores the result of a query physically.
   - Data is not automatically updated when the underlying tables change.
   - Must be refreshed manually or on a schedule.
   - Provides faster access to the data, especially for complex queries.

   When to use a View:
   1. When you always need the most up-to-date data.
   2. For simple queries where performance isn't a major concern.
   3. To provide a layer of abstraction or security over the underlying tables.

   When to use a Materialized View:
   1. For complex queries that are computationally expensive but don't need real-time data.
   2. When you need to improve query performance for read-heavy workloads.
   3. For data that doesn't change frequently.
   4. In data warehousing scenarios for pre-computing and storing aggregate data.

   The choice between Views and Materialized Views depends on the balance between data freshness requirements and query performance needs in your specific use case.

