---
layout: home
parent: Rails
grand_parent: Ruby
title: Active Record
---

# Active Record

ActiveRecord is the database interface in Rails. 

It provides an object-oriented interface to your database tables and allows you to perform operations on them using Ruby code. Some key features of ActiveRecord include:

## ORM

ORM stands for Object-Relational Mapping. It is a programming technique used to map data between a relational database and an object-oriented programming language.

ORM frameworks provide a way for developers to interact with a database using high-level programming constructs such as classes, objects, and methods. The ORM maps these constructs to the underlying database schema and handles the translation of data back and forth between the two systems.

```ruby
class Book < ApplicationRecord
  self.table_name = "books"

  attribute :title, :string
  attribute :author, :string
  attribute :published_date, :date
end
```

## Models

A model represents a table in your database and provides an interface to the data in that table. 

Each instance of a model represents a row in the table. Models are defined as Ruby classes that inherit from the ActiveRecord::Base class. You can use methods on the model class to query and manipulate the data in the associated table.

## Migrations

Migrations are a way of managing changes to your database schema over time. 

They allow you to create, modify, and delete tables and columns, and provide a way of tracking and reverting changes. Migrations are defined as Ruby files and can be run using the `rails db:migrate` command.

## Associations 

Associations are a way of defining relationships between models. 

There are several types of associations in ActiveRecord, including `belongs_to`, `has_one`, `has_many`, and `has_many :through`. Associations are defined using methods on the model class, and allow you to easily navigate between related records.

## Validations

Validations are a way of ensuring that data meets certain criteria before it is saved to the database. 

There are many types of validations in ActiveRecord, such as presence, length, numericality, and format. Validations are defined using methods on the model class.

### Example

```ruby
class Product < ApplicationRecord
  # Attributes
  attribute :name, :string
  attribute :description, :text
  attribute :price, :decimal, precision: 10, scale: 2

  # Scopes
  scope :cheap, -> { where('price < ?', 50) }
  scope :expensive, -> { where('price >= ?', 50) }

  # Validations
  validates :name, presence: true, length: { maximum: 255 }
  validates :description, presence: true
  validates :price, presence: true, numericality: { greater_than_or_equal_to: 0 }

  # Methods
  def formatted_price
    format('$%.2f', price)
  end

  def self.search(query)
    where('name ILIKE ?', "%#{query}%")
  end
end

```

## Single Table Inheritance

Single Table Inheritance (STI) is a technique used in object-oriented programming to store objects of different subclasses in the same database table. 

In STI, each row in the table represents an object of a specific subclass, and a type column is used to differentiate between the different subclasses.

```ruby
class Product < ApplicationRecord
end

class Book < Product
end

class Movie < Product
end

class MusicAlbum < Product
end
```

In database

```ruby
create_table :products do |t|
  t.string :title
  t.string :type
  # other attributes
end
```

