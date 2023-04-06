# Ruby

- Dynamic, reflective, general purpose, open source
- Focuses on simplicity and productivity

## Main 

### Key features

- Object-oriented
- Flexible
- Dynamic typing and Duck typing
- Garbage collector
- Keyword arguments

### Ruby vs Python

|                                   | Ruby | Python |
|-----------------------------------|------|--------|
| High level language               | X    | X      |
| Support multiple platforms        | X    | X      |
| Use interactive prompt called irb | X    | X      |
| Server side scripting language    | X    | X      |
| Fully object oriented             | X    |        |
| Mixins                            | X    |        |
| Blocks, procs and lambdas         | X    |        |

### Types of variables

- Local variable
- Class variable
- Instance variable
- Global variable

## Blocks

### Block

Ruby code blocks are called closures in other programming languages. It consist of a group of codes which is always enclosed with braces or written between do...end.

### Yield

The yield statement is used to call a block within a method with a value.

```ruby
def explicit_block(&block)
  block.call # same as yield
end
explicit_block { puts "Explicit block called" }
```

### block_given?

If you try to yield without a block you will get a no block given (yield) error.

```ruby
def do_something_with_block
  return "No block given" unless block_given?
  yield
end
```

### Lambda

A lambda is a way to define a block & its parameters with some special syntax.

You can save this lambda into a variable for later use.

```ruby
say_something = -> { puts "This is a lambda" }
```

```ruby
my_lambda.call
my_lambda.()
my_lambda[]
my_lambda.===
```

### Proc

There is no dedicated Lambda class. A lambda is just a special Proc object. If you take a look at the instance methods from Proc, you will notice there is a lambda? method.

```ruby
my_proc = Proc.new { |x| puts x }
```

### Lambdas vs Procs

- Lambdas are defined with -> {} and procs with Proc.new {}.
- Procs return from the current method, while lambdas return from the lambda itself.
- Procs don’t care about the correct number of arguments, while lambdas will raise an exception.

### Closure

Ruby procs & lambdas also have another special attribute. When you create a Ruby proc, it captures the current execution scope with it.

This concept, which is sometimes called closure, means that a proc will carry with it values like local variables and methods from the context where it was defined.

## Other

### &

Explain ampersand parameter (&block) in Ruby.
The &block is a way to pass a reference (instead of a local variable) to the block to a method.

Here, block word after the & is just a name for the reference, any other name can be used instead of this.

### Mixin

Ruby doesn't support multiple inheritance. Modules eliminate the need of multiple inheritance using mixin in Ruby.

A module doesn't have instances because it is not a class. However, a module can be included within a class.

### DSL

A Domain Specific Language is an API that allows a developer to solve a problem or represent data more naturally than they might otherwise. The flexible nature of Ruby's syntax and the ability to alias and alter existing methods and classes makes it conducive to creating rich DSL's.
