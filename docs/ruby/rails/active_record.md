---
layout: home
parent: Rails
title: Active Record
---

# Active Record

ActiveRecord is the database interface in Rails. 

It provides an object-oriented interface to your database tables and allows you to perform operations on them using Ruby code. Some key features of ActiveRecord include:

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

