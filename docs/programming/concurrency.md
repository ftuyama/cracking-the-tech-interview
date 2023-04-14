---
layout: home
parent: Programming
title: Concurrency
---

# Concurrency vs Parallelism

Concurrency and parallelism are two concepts that are often used in the context of computer programming and software development.

## Concurrency

Concurrency refers to the ability of a system to perform multiple tasks or processes simultaneously, without necessarily executing them at the same time. 

In other words, a concurrent system may appear to be executing multiple tasks at the same time, but in reality, it is switching rapidly between different tasks to give the impression of parallelism.

### Example

In a multi-threaded program, multiple threads may be running concurrently on the same processor, but only one thread can execute at a time. 

The operating system scheduler switches rapidly between different threads, giving the impression that they are all executing in parallel.

## Parallelism

Parallelism, on the other hand, refers to the ability of a system to execute multiple tasks or processes at the same time, using multiple processors or cores. 

In a parallel system, each processor or core can execute a different task simultaneously, allowing for true parallelism.

# Example

In a parallel computing system, a single computation can be broken down into smaller sub-tasks, which can be executed simultaneously on different processors or cores, allowing the computation to be completed much faster than it would be on a single processor.
