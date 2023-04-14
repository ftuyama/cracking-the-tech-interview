---
layout: home
parent: Ruby
title: Garbage Collector
---
  
# Garbage Collector

In Ruby, the garbage collector is responsible for managing memory allocation and deallocation of objects during runtime. It automatically frees up memory that is no longer being used by objects in the program, thereby preventing memory leaks and other memory-related errors.

## Mark-and-Sweep

The garbage collector in Ruby uses a mark-and-sweep algorithm to determine which objects are no longer being used and can be freed up. Here's how it works:

- **Mark phase**: The garbage collector starts by marking all objects that are still being used by the program. It does this by traversing the object graph, starting from the root objects (such as local variables, instance variables, and global variables), and marking any objects that are reachable from them.

- **Sweep phase**: Once all live objects have been marked, the garbage collector sweeps through the heap and frees up any memory that is not marked as live. This involves deallocating memory used by objects that are no longer being used by the program.

## Generational algorithm

In addition to the mark-and-sweep algorithm, Ruby also employs a generational garbage collector that divides objects into different generations based on their age. New objects are created in the "young" generation, which is garbage collected more frequently than the "old" generation. This allows the garbage collector to quickly identify and collect short-lived objects, while reducing the overhead of garbage collection on long-lived objects.
