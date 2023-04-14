---
layout: home
parent: Ruby
title: Event Machine
---

# EventMachine

EventMachine is a Ruby library for building event-driven and scalable network applications. Its main points are:

Overall, EventMachine is a powerful and flexible library for building event-driven and scalable network applications in Ruby. Its focus on non-blocking I/O and event-driven architecture allows for high-performance and efficient use of system resources, making it a popular choice for building real-time applications.

## Key features

- **Event-driven architecture**: EventMachine uses an event loop to manage the processing of network events, such as socket connections and data transfers. This allows for efficient use of system resources and supports a high number of concurrent connections.
- **Non-blocking I/O**: EventMachine uses non-blocking I/O to enable efficient and scalable network communication. This means that multiple network requests can be processed concurrently without blocking the execution of other code.
- **High-performance and scalability**: EventMachine is designed to support high-performance and scalable network applications, such as web servers, chat servers, and other real-time applications. Its event-driven architecture and non-blocking I/O allow it to handle a large number of connections and data transfers.
- **Support for multiple protocols**: EventMachine supports a variety of network protocols, including TCP, UDP, SSL, and HTTP. This makes it a versatile choice for building a wide range of network applications.
- **Ruby-based API**: EventMachine provides a Ruby-based API that is easy to use and familiar to Ruby developers. It also integrates with a variety of Ruby frameworks and libraries, such as Ruby on Rails and Sinatra, allowing for easy integration with existing codebases.

## Async Programming 

In Ruby, async programming is often implemented using the concept of "async/await" or "coroutines". This allows code to be written in a synchronous-looking style while still executing asynchronously.

These libraries provide tools for performing non-blocking I/O and other tasks, as well as for managing and coordinating multiple tasks in an async environment:

- EventMachine
- Celluloid
- Async gem

### Example

```ruby
require 'async'

def fetch_data(url)
  Async do |task|
    response = task.async do
      Net::HTTP.get_response(URI(url))
    end

    body = task.async do
      response.body
    end

    [response, body]
  end
end

response, body = fetch_data('https://www.example.com').wait

puts "Response code: #{response.code}"
puts "Body length: #{body.length}"
```
