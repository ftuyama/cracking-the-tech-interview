---
layout: home
parent: Programming
title: Object Oriented
---

# Object Oriented Programming

- **Class**: Blueprint for creating objects
- **Object**: Instance of a class
- **Inheritance**: New class derived from existing class
- **Polymorphism**: Object of different classes treated as the same class
- **Encapsulation**: Hiding internal details of an object from outside
- **Abstraction**: Focusing on essential qualities of an object

## Ruby specific

- **Duck Typing**: A type of dynamic typing where the type of an object is determined by its behavior (i.e., whether it responds to certain methods), rather than its class.
- **Blocks**: A block is a chunk of code that can be passed as an argument to a method in Ruby. They are a way to pass behavior into a method, similar to how lambdas or anonymous functions work in other languages.
- **Modules**: A module is a container for a set of methods and constants, similar to a class. However, modules cannot be instantiated and are used primarily for namespacing and mixing in behavior to classes through the "include" keyword.
- **Mixins**: Mixins are a way to add behavior to a class without inheritance. A module can be mixed into a class using the "include" keyword, and its methods become available to instances of the class.
- **Metaprogramming**: Metaprogramming refers to writing code that can modify itself or other code at runtime. In Ruby, this is made possible by the language's support for introspection and dynamic dispatch, which allow for powerful programming techniques such as defining methods at runtime and modifying the behavior of classes and objects on the fly.

## Advantages

- **Modularity**: OOP emphasizes the use of objects, which are self-contained modules that encapsulate data and behavior. This makes it easier to build complex systems by breaking them down into smaller, more manageable parts.
- **Reusability**: OOP encourages the creation of reusable code, which can save time and effort when developing new applications. Objects can be easily adapted and extended to fit new use cases.
- **Flexibility**: OOP allows for polymorphism, which means that objects can take on different forms and behave differently in different contexts. This makes it easier to write code that can handle a wide range of inputs and use cases.
- **Maintainability**: OOP makes it easier to maintain code over time by encapsulating data and behavior into objects. This reduces the likelihood of bugs and makes it easier to fix them when they do occur.
- **Code organization**: OOP promotes a more organized approach to coding, with objects and classes providing a natural way to structure code. This can make it easier to understand and maintain large codebases.
- **Easier debugging**: OOP makes it easier to debug code because objects encapsulate data and behavior in a self-contained unit. This makes it easier to isolate problems and test specific parts of the code.

## Disadvantages

- **Complexity**: OOP can be more complex than other programming paradigms, especially for beginners. The concepts of classes, objects, and inheritance can be difficult to understand and apply correctly.
- **Performance overhead**: OOP can have a performance overhead compared to other programming paradigms, especially when dealing with large datasets or complex algorithms. This is due to the overhead of creating and managing objects.
- **Steep learning curve**: OOP can be challenging to learn, especially for developers who are used to procedural programming. The concepts of abstraction, encapsulation, and inheritance can be difficult to master.
- **Overuse of inheritance**: In some cases, developers can overuse inheritance, leading to overly complex and tightly coupled code. This can make it harder to maintain and modify code over time.
- **Lack of support for functional programming**: OOP languages often lack support for functional programming constructs, such as higher-order functions and immutability. This can make it harder to write code for certain types of applications.
- **Difficulty with certain types of problems**: OOP is not always the best choice for solving certain types of problems, such as those that involve a lot of data manipulation or require low-level control over hardware.

## Links

[Polymorphism in Ruby]({% link docs/ruby/polymorphism.md %})
