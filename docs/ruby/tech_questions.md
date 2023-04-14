---
layout: home
parent: Ruby
title: Tech Questions
---

# Tech Questions

Silly questions no one uses, but... <https://www.toptal.com/ruby/interview-questions>

## Garbage Collector

In Ruby, the garbage collector is responsible for managing memory allocation and deallocation of objects during runtime. It automatically frees up memory that is no longer being used by objects in the program, thereby preventing memory leaks and other memory-related errors.

### Mark-and-Sweep

The garbage collector in Ruby uses a mark-and-sweep algorithm to determine which objects are no longer being used and can be freed up. Here's how it works:

- **Mark phase**: The garbage collector starts by marking all objects that are still being used by the program. It does this by traversing the object graph, starting from the root objects (such as local variables, instance variables, and global variables), and marking any objects that are reachable from them.

- **Sweep phase**: Once all live objects have been marked, the garbage collector sweeps through the heap and frees up any memory that is not marked as live. This involves deallocating memory used by objects that are no longer being used by the program.

### Generational algorithm

In addition to the mark-and-sweep algorithm, Ruby also employs a generational garbage collector that divides objects into different generations based on their age. New objects are created in the "young" generation, which is garbage collected more frequently than the "old" generation. This allows the garbage collector to quickly identify and collect short-lived objects, while reducing the overhead of garbage collection on long-lived objects.

## Concurrency and Parallelism

- Concurrency in Ruby is typically achieved using threads. Ruby has built-in support for threading, which allows multiple threads to execute concurrently within the same process. 

- Parallelism in Ruby is typically achieved using multiple processes. Ruby supports forking, which allows a process to create multiple child processes that can execute in parallel.

## And vs &&

The difference is the precedence of the operator

```ruby
val1 = true and false  # hint: output of this statement in IRB is NOT value of val1!
val2 = true && false
```

```ruby
(val1 = true) and false    # results in val1 being equal to true
val2 = (true && false)     # results in val2 being equal to false
```

## Clone vs dup

Both create a shallow copy of an object, it will not copy any mixed-in module methods

- Object#clone - the instance variables that refer to mutable objects will refer to the same objects as the original object
- Object#dup - the instance variables that refer to mutable objects will refer to new copies of the objects
- Marshal - to make a deep copy of an object that contains mutable objects, you can use the Marshal module

```ruby
deep_copy = Marshal.load(Marshal.dump(original_object))
```

You can also create a recursive `deep_dup` function:

```ruby
class Array
  def deep_dup
    map { |element| element.respond_to?(:deep_dup) ? element.deep_dup : element.dup }
  end
end
```

## Include vs Extend

- include mixes in specified module methods as instance methods in the target class
- extend mixes in specified module methods as class methods in the target class

## Inline Fibonacci sequence

(1..20).inject( [0, 1] ) { | fib | fib << fib.last(2).inject(:+) }

## Explain how & works

When a parameter is passed with & in front of it (indicating that is it to be used as a block), Ruby will call to_proc on it in an attempt to make it usable as a block. Symbol#to_proc quite handily returns a Proc that will invoke the method of the corresponding name on whatever is passed to it, thus enabling our little shorthand trick to work.
