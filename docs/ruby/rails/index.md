---
layout: home
parent: Ruby
title: Rails
has_children: true
---

# Rails

- **Model-View-Controller (MVC)**: Rails follows the MVC architectural pattern, which separates an application into three interconnected components**: the model (handles data), the view (displays data), and the controller (handles user input).
- **Convention over Configuration**: Rails favors convention over configuration, which means that it makes assumptions about how an application is structured and how it should behave. This reduces the amount of code that developers need to write, and makes it easy to get up and running quickly.
- **Active Record**: Rails has an object-relational mapping (ORM) library called Active Record, which provides an interface to a database. It allows developers to interact with a database using Ruby objects instead of SQL.
- **RESTful Routing**: Rails encourages the use of RESTful routes, which map HTTP verbs (such as GET, POST, PUT, and DELETE) to CRUD (Create, Read, Update, Delete) operations on resources.
- **Scaffolding**: Rails has a feature called scaffolding, which generates code for a basic CRUD interface for a model. This can be a useful starting point for new applications.
- **Asset Pipeline**: Rails has an asset pipeline that allows developers to manage and preprocess their application's assets (such as stylesheets and JavaScript files).
- **Testing Framework**: Rails has a built-in testing framework that allows developers to write tests for their application. This includes support for unit tests, functional tests, and integration tests.
- **Action Mailer**: Rails has a library called Action Mailer, which allows developers to send and receive email from their application.
- **Internationalization (i18n)**: Rails has built-in support for internationalization, which allows developers to translate their application into different languages.
- **Security Features**: Rails includes several security features, such as protection against cross-site scripting (XSS) and cross-site request forgery (CSRF) attacks.
- **API Mode**: Rails has an API mode that allows developers to create APIs without the overhead of a full web application.
- **Active Job**: Rails has a library called Active Job, which provides a unified interface for working with background jobs.
- **Turbo Streams**: Rails 7 introduced a feature called Turbo Streams, which allows developers to update a web page's content in real-time without requiring a full page refresh.

## Rake

Rake is a Ruby Make; it is a Ruby utility that replaces the Unix utility 'make' and builds a list of tasks using a 'Rakefile' and '.rake files'. Rake is used in Rails for routine administration activities such as database migration via scripts, schema loading into the database, and so on.

## Rails Controller

The Rails controller serves as the application's logical heart. It makes the interaction between users, views, and the model easier. It also does other tasks such as:

- It can route external requests to internal actions. It is highly adept at handling URLs. It governs helper modules, which extend the capabilities of view templates without bloating their code.
- It manages sessions, which give consumers the sense that they are interacting with our applications in real-time.

## Observer vs Callback

- Observers: Similar to Callback, Observers are used when the method is not directly related to the object lifecycle. In addition, the observer has a longer lifespan and can be detached or attached at any time. For example, displaying model values in the UI and updating the model based on user input.
- Callback: This method can be called at specific points in an object's life cycle, such as when an object is validated, created, updated, or removed. A callback is a short-lived method. For example, consider operating a thread and providing a call-back function that is invoked after the thread terminates.
