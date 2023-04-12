---
layout: home
parent: Rails
grand_parent: Ruby
title: Indexes
---

# Index 

Indexes are database structures that optimize queries by making it faster to search and retrieve data from a table. 

In Rails, indexes can be added to database tables to speed up queries and improve overall application performance.

## Creating

```ruby
class AddIndexToUsersEmail < ActiveRecord::Migration[6.0]
  def change
    add_index :users, :email
  end
end
```

## Conccurent

Adding an index to a large table can take a long time and may block other operations from being performed on the table.

In order to add an index to a table without blocking other operations, you can use a feature called `concurrent indexing`.

To create an index concurrently in Rails, you can use the add_index method with the algorithm: :concurrently option, like this:

```ruby
class AddIndexToUsersEmail < ActiveRecord::Migration[6.0]
  disable_ddl_transaction!

  def change
    add_index :users, :email, algorithm: :concurrently
  end
end
```

## Foreign keys

In general, all foreign keys should always be indexed in Ruby on Rails.

Foreign keys are columns in a table that refer to the primary key of another table, establishing a relationship between the two tables. Indexing foreign keys can significantly improve the performance of queries that join tables based on those keys.

When a foreign key is indexed, the database can use that index to quickly look up the rows in the referencing table that match a particular value in the referenced table. This can avoid the need for a slow full table scan, especially when dealing with large tables.

In Ruby on Rails, you can add an index to a foreign key column by creating a migration and using the add_index method. For example, to add an
