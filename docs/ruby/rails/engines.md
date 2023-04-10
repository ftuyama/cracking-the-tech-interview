---
layout: home
parent: Rails
grand_parent: Ruby
title: Engines
---


Rails Engines
=============

Rails engines are a way of packaging and distributing functionality as self-contained, reusable components within a larger Rails application.

What is a Rails Engine?
-----------------------

A Rails engine is essentially a mini Rails application that can be mounted within a larger Rails application. It can include models, controllers, views, routes, assets, database migrations and other components just like a regular Rails application. However, it is designed to be packaged and reused independently of any specific application.

Why use Rails Engines?
----------------------

Rails engines provide a way to organize code into reusable components, which can be useful in a variety of scenarios:

*   **Modular architecture**: If you have a large Rails application that is becoming unwieldy, you can use engines to break it down into smaller, more manageable pieces. Each engine can represent a specific domain or functionality, making it easier to reason about and maintain the codebase.
*   **Plugin-like functionality**: Engines can be used to add new functionality to a Rails application without having to modify the core code. This is similar to the concept of plugins in other systems, but with the added benefit of being able to share the plugin across multiple applications.
*   **Component sharing**: If you have multiple Rails applications that need to share a common set of functionality, you can extract that functionality into an engine and include it in each application.

Creating a Rails Engine
-----------------------

To create a new Rails engine, you can use the `rails plugin new` command:

sqlCopy code

`rails plugin new my_engine --mountable`

This will create a new engine in the `my_engine` directory, with the `--mountable` option indicating that it should be mountable within another Rails application.

From there, you can add models, controllers, views, and other components just like you would in a regular Rails application.

Mounting a Rails Engine
-----------------------

To mount a Rails engine within a larger Rails application, you can use the `mount` method in your `config/routes.rb` file:

rubyCopy code

`Rails.application.routes.draw do   mount MyEngine::Engine => "/my_engine" end`

This will mount the `MyEngine` engine at the `/my_engine` route within your application.

Conclusion
----------

Rails engines provide a powerful way to organize and share code within a larger Rails application. By breaking down functionality into reusable components, you can create a more modular, maintainable codebase that is easier to reason about and extend over time.
