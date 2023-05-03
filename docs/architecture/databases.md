---
layout: home
parent: Architecture
title: Databases
---

# Databases

<img width="850" alt="image" src="https://user-images.githubusercontent.com/11530478/235827108-9f21b049-b5ad-4847-9ffc-f567d86d8db3.png">

![image](https://user-images.githubusercontent.com/11530478/235827117-0f905627-6369-4ae1-ae5f-e90d36741677.png)

## Relational Databases

Relational databases are based on the relational model, which organizes data into tables with rows and columns. 

These databases have been the standard choice for many applications due to their robust consistency, support for complex queries, and adherence to ACID properties (Atomicity, Consistency, Isolation, Durability).

### Pros

- **Structured data organization**: Data in relational databases is stored in tables with a predefined schema, enforcing a consistent structure throughout the database. This organization makes it easier to manage and maintain data, especially when dealing with large amounts of structured data.
- **Relationships and referential integrity**: The relationships between tables in a relational database are defined by primary and foreign keys, ensuring referential integrity. This feature allows for efficient querying of related data and supports complex data relationships.
- **SQL support**: Relational databases use Structured Query Language (SQL) for querying, manipulating, and managing data. SQL is a powerful and widely adopted language that enables developers to perform complex queries and data manipulations.
- **Transactions and ACID properties**: Relational databases support transactions, which are sets of related operations that either succeed or fail as a whole. This feature ensures the ACID properties – Atomicity, Consistency, Isolation, and Durability – are maintained, guaranteeing data consistency and integrity.
- **Indexing and optimization**: Relational databases offer various indexing techniques and query optimization strategies, which help improve query performance and reduce resource consumption.

### Cons

- **Limited scalability**: Scaling relational databases horizontally (adding more nodes) can be challenging, especially when compared to some NoSQL databases that are designed for distributed environments.
- **Rigidity**: The predefined schema in relational databases can make it difficult to adapt to changing requirements, as altering the schema may require significant modifications to existing data and applications.
- **Performance** issues with large datasets: As the volume of data grows, relational databases may experience performance issues, particularly when dealing with complex queries and large-scale data manipulations.
- **Inefficient for unstructured or semi-structured data**: Relational databases are designed for structured data, which may not be suitable for managing unstructured or semi-structured data, such as social media data or sensor data.

### Market

![image](https://user-images.githubusercontent.com/11530478/235827320-64a75baf-09db-4838-830c-9eebd24f0721.png)


## Reference

<https://blog.bytebytego.com/p/understanding-database-types>
