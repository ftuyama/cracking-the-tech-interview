---
layout: home
parent: Ruby
title: Rack
---

# Rack

Rack is a Ruby web server interface that sits between web servers and web frameworks, allowing them to communicate with each other in a standardized way. It provides a simple and modular API that abstracts away the low-level details of web server communication, such as parsing HTTP requests and generating HTTP responses.

With Rack, developers can write web applications that can be run on any Rack-compliant web server, such as WEBrick, Thin, or Puma, and can be built using any Rack-compliant web framework, such as Ruby on Rails or Sinatra. This modularity and compatibility allow for easy integration of different components and flexibility in choosing the appropriate technology for a particular task.

Rack also provides middleware, which are components that can be inserted into the request/response pipeline to perform tasks such as authentication, caching, or compression. This middleware architecture allows for easy customization and extension of web applications, as well as sharing of common functionality across different applications.

![image](https://user-images.githubusercontent.com/11530478/230244773-ac3fd96e-ff41-4b26-a0f3-485cd3ee1b07.png)

## Definition

Rack defines a very simple interface. Rack compliant code must have the following three characteristics:
- It must respond to call
- The call method must accept a single argument - This argument is typically called env or environment, and it bundles all of the data about the request.
- The call method must return an array of three elements These elements are, in order, status for the HTTP status code, headers, and body for the actual content of the response.
A nice side effect of the call interface is that procs and lambdas can be used as Rack objects.

## Call

The call method is called in Rack, which is also called in all Rack middleware.

The call method is a fundamental method in the Rack specification, which defines the interface between Ruby web frameworks and web servers. The call method is responsible for handling an HTTP request and generating an HTTP response.

All Rack middleware are Ruby classes that conform to the Rack specification, and they are typically used to modify the request or response in some way before or after it reaches the main application. Each middleware component in the middleware stack must implement the call method, and the method is called in order from top to bottom of the middleware stack.

The call method takes a single argument, which is a hash representing the request environment. The method must return an array containing the response status code, headers, and body.

So, the call method is the core of the Rack specification and is responsible for handling HTTP requests and responses in Ruby web applications.
