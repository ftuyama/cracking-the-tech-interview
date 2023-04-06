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

### Polymorphism

```ruby
class Animal
  def speak
    "Animal speaks!"
  end
end

class Dog < Animal
  def speak
    "Woof!"
  end
end

class Cat < Animal
  def speak
    "Meow!"
  end
end

class Cow < Animal
  # Inherits Animal's speak method
end

animals = [Dog.new, Cat.new, Cow.new]

animals.each do |animal|
  puts animal.speak
end
```



