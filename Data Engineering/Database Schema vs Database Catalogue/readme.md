
# Database Schema

## Definition

A Database Schema is a logical blueprint that defines how data is organized and structured in a database. It includes tables, relationships, constraints, and other elements that determine how data is stored and accessed.

## Key Components

- **Tables:** Define the structure of data storage (e.g., columns, data types).
- **Relationships:** Define how tables are connected (e.g., primary keys, foreign keys).
- **Constraints:** Rules applied to data (e.g., unique, not null, check constraints).
- **Indexes:** Improve query performance by enabling faster data retrieval.
- **Views:** Virtual tables created from queries on one or more tables.

## Purpose

- Provides a logical framework for organizing data.
- Ensures data integrity and consistency through constraints and relationships.
- Acts as a blueprint for database design and development.

## Example

In a Sales Database Schema, you might have:
- A Customers table with columns like CustomerID, Name, and Email.
- An Orders table with columns like OrderID, CustomerID, and OrderDate.
- A relationship between Customers and Orders using CustomerID as a foreign key.

---

# Database Catalog

## Definition

A Database Catalog is a system-level component that stores metadata about the database. It contains information about the database's structure, objects, and configurations.

## Key Components

- **Metadata:** Information about database objects (e.g., tables, views, indexes).
- **System Tables:** Tables that store metadata (e.g., information_schema in MySQL, pg_catalog in PostgreSQL).
- **Object Definitions:** Details about the structure and properties of database objects.
- **User Information:** Data about users, roles, and permissions.

## Purpose

- Acts as a centralized repository for metadata.
- Helps the database management system (DBMS) manage and access database objects.
- Enables users and applications to query metadata for database exploration and management.

## Example

In a Database Catalog, you might find:
- Metadata about the Customers table, such as its columns (CustomerID, Name, Email) and their data types.
- Information about user permissions, such as which users can access the Orders table.
- Details about indexes, such as the index on the CustomerID column.



## Database Schema vs. Database Catalog

| Feature            | Database Schema | Database Catalog |
|--------------------|----------------|------------------|
| **Definition**     | Logical structure of a database, defining tables, columns, relationships, constraints, etc. | A collection of schemas and metadata that describe the entire database system. |
| **Scope**         | Specific to a single schema within the database. | Covers the entire database, including multiple schemas. |
| **Contains**      | Tables, views, indexes, constraints, stored procedures. | Information about schemas, tables, users, access privileges, and storage. |
| **Purpose**       | Defines how data is organized and structured in a specific schema. | Manages metadata and system-wide information about the database. |
| **Example**       | A schema named `sales` containing tables like `customers`, `orders`, and `products`. | A catalog storing details about the `sales` schema, including its tables and permissions. |
| **Usage**         | Developers and DBAs use schemas to structure and organize data. | The database system uses the catalog to manage schemas and access controls. |

For example, the schema defines the Customers table, and the catalog stores information about its columns, data types, and relationships.

The catalog helps the DBMS understand and manage the schema.

--- 

Notes: From [stackoverflow](https://stackoverflow.com/questions/7022755/whats-the-difference-between-a-catalog-and-a-schema-in-a-relational-database)

## Cluster > Catalog > Schema > Table > Columns & Rows

So in both Postgres and the SQL Standard we have this containment hierarchy:

- A computer may have one cluster or multiple.
    - A database server is a cluster.
- A cluster has catalogs. ( Catalog = Database )
- Catalogs have schemas. (Schema = namespace of tables, and security boundary)
- Schemas have tables.
- Tables have rows.
- Rows have values, defined by columns.
    - Those values are the business data your apps and users care about such as person's name, invoice due date, product price, gamer’s high score. The column defines the data type of the values (text, date, number, and so on).

<img src = "https://i.sstatic.net/FqyMq.png">