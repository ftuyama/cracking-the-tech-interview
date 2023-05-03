---
layout: home
title: Architecture
has_children: true
---

# Architecture

![image](https://user-images.githubusercontent.com/11530478/235828850-fe044559-66fd-472a-8445-56eeb32cff08.png)

## Async communication

### Technologies

There are several technologies you can use for async communication with Ruby. Here are a few examples:

- **Async/Await**: As of Ruby 3.0, Ruby has native support for asynchronous programming with the async/await syntax. This allows you to write asynchronous code using familiar synchronous programming patterns.
- **EventMachine**: EventMachine is a popular Ruby library for building network applications that require high performance and scalability. It provides an event-driven architecture that allows for non-blocking I/O and supports a variety of protocols, such as TCP, UDP, and HTTP.
- **Celluloid**: Celluloid is a concurrency framework for Ruby that allows you to build concurrent and distributed systems with ease. It provides an actor-based model of concurrency, which allows you to write asynchronous code that is easy to reason about.
- **Sidekiq**: Sidekiq is a popular Ruby background job processing framework that uses Redis for async communication. It allows you to easily offload CPU-intensive tasks to worker processes, which can run in the background and free up your application's main thread.
- **WebSockets**: WebSockets are a protocol for bi-directional, real-time communication between web browsers and servers. There are several Ruby libraries that support WebSockets, such as Faye and Action Cable.

### Message Queue

- **RabbitMQ**: RabbitMQ is a popular open-source message broker that implements the Advanced Message Queuing Protocol (AMQP). It supports a variety of messaging patterns, such as publish/subscribe and request/reply, and is widely used in enterprise and cloud environments.
- **Apache Kafka**: Apache Kafka is a distributed streaming platform that can be used for building real-time data pipelines and streaming applications. It supports high-throughput, low-latency message delivery and is designed to handle large amounts of data.
- **Amazon Simple Queue Service (SQS)**: Amazon SQS is a fully-managed message queuing service that enables you to decouple and scale microservices, distributed systems, and serverless applications. It provides reliable, scalable, and cost-effective message delivery and supports both standard and FIFO queues.
- **Redis**: Redis is an in-memory data structure store that can also be used as a message broker. It provides support for Pub/Sub messaging, which allows for broadcasting messages to multiple subscribers. Redis can be used as a lightweight message queue or as a high-performance cache.


## Monitoring

### Technologies

- **New Relic**: New Relic is a popular application performance monitoring (APM) tool that provides real-time monitoring and analysis of your Ruby application's performance. It provides detailed metrics on response time, throughput, error rates, and database performance, as well as the ability to drill down to specific transactions and code segments.
- **Datadog**: Datadog is a cloud-based monitoring platform that provides real-time visibility into your Ruby application's performance and infrastructure. It supports APM, infrastructure monitoring, log management, and user experience monitoring, as well as integrations with over 400 other technologies.
- **Kibana**: Kibana is a data visualization tool that is often used in conjunction with Elasticsearch, a search and analytics engine. It provides a web interface for exploring and visualizing data stored in Elasticsearch, including logs, metrics, and other performance data. Kibana allows you to create custom dashboards and visualizations, and provides a powerful query language for filtering and analyzing data.
- **Sentry**: Sentry is an error tracking platform that provides real-time error monitoring and alerting for your Ruby application. It captures and aggregates errors and exceptions, providing detailed information on the root cause, context, and impact of each issue. Sentry also provides integration with popular communication tools such as Slack and email to alert the team on any error and facilitate quick resolution of issues.
