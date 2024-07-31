# PostgreSQL Technical Documentation

## Introduction

PostgreSQL, often simply "Postgres", is an advanced, open-source object-relational database system. It supports both SQL (relational) and JSON (non-relational) querying.

## Key Features

1. ACID Compliance: Ensures data validity despite errors, power failures, etc.
2. Transactions: Supports complex transactions and multi-version concurrency control.
3. Extensibility: Users can add new functions, data types, etc.
4. Inheritance: Tables can inherit characteristics from a "parent" table.
5. Sophisticated query planner/optimizer: Efficiently handles complex queries.

## Basic Concepts

### Databases and Schemas
- A PostgreSQL server can host multiple databases
- A schema is a namespace within a database that contains named objects like tables, views, etc.

### Tables
Tables are the main objects used to hold data. Basic table creation:

```sql
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    username VARCHAR(50) UNIQUE NOT NULL,
    email VARCHAR(255) UNIQUE NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

### Data Types
PostgreSQL supports various data types including:
- Numeric: INTEGER, BIGINT, NUMERIC
- Character: CHAR, VARCHAR, TEXT
- Date/Time: DATE, TIME, TIMESTAMP
- Boolean: BOOLEAN
- Arrays
- JSON and JSONB

### Indexes
Indexes improve database performance. Basic index creation:

```sql
CREATE INDEX idx_username ON users(username);
```

## SQL Basics

### SELECT
Retrieve data from tables:

```sql
SELECT * FROM users WHERE id = 1;
```

### INSERT
Add new rows to a table:

```sql
INSERT INTO users (username, email) VALUES ('johndoe', 'john@example.com');
```

### UPDATE
Modify existing rows:

```sql
UPDATE users SET email = 'newemail@example.com' WHERE id = 1;
```

### DELETE
Remove rows from a table:

```sql
DELETE FROM users WHERE id = 1;
```

## Advanced Features

### Transactions
Group multiple operations:

```sql
BEGIN;
UPDATE accounts SET balance = balance - 100 WHERE id = 1;
UPDATE accounts SET balance = balance + 100 WHERE id = 2;
COMMIT;
```

### Views
Virtual tables based on the result of a SQL statement:

```sql
CREATE VIEW active_users AS SELECT * FROM users WHERE last_login > CURRENT_DATE - INTERVAL '30 days';
```

### Stored Procedures
Custom functions that can be reused:

```sql
CREATE FUNCTION increment(i INTEGER) RETURNS INTEGER AS $$
        BEGIN
                RETURN i + 1;
        END;
$$ LANGUAGE plpgsql;
```

### Triggers
Automatically executed functions based on database events:

```sql
CREATE TRIGGER update_timestamp BEFORE UPDATE ON users
FOR EACH ROW EXECUTE FUNCTION update_modified_column();
```

## Performance Tuning

1. Proper indexing
2. Regular VACUUM and ANALYZE
3. Partitioning large tables
4. Query optimization
5. Configuration tuning (e.g., shared_buffers, work_mem)

## Backup and Recovery

- pg_dump: Logical backups
- pg_basebackup: Physical backups
- Point-in-Time Recovery (PITR)

## Security

- SSL connections
- Client authentication
- Role-based access control
- Row-level security

## Replication

- Streaming replication for high availability
- Logical replication for selective data replication

