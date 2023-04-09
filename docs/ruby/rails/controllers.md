---
layout: home
parent: Rails
title: Controllers
---

# Controllers

Controllers are the glue between the model and the view in Rails. 

They handle user input and manage the flow of data between the model and the view. Some key features of controllers include

## Actions

An action is a method in a controller that handles a user request. 

Actions typically correspond to URLs in your application, and can render views, redirect to other URLs, set flash messages, and more.

## Filters

Filters are a way of specifying code that should be executed before or after a particular action. 

They can be used to authenticate users, set up database connections, and perform other tasks. Filters are defined using methods such as `before_action`, `after_action`, and `around_action`.
