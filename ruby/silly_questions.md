# Silly Questions

Silly questions no one uses, but... <https://www.toptal.com/ruby/interview-questions>

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

- Object#dup creates a shallow copy of an object (it will not copy any mixed-in module methods)
- Object#clone will 

## Include vs Extend

- include mixes in specified module methods as instance methods in the target class
- extend mixes in specified module methods as class methods in the target class

## Inline Fibonacci sequence

(1..20).inject( [0, 1] ) { | fib | fib << fib.last(2).inject(:+) }

## Explain how & works

When a parameter is passed with & in front of it (indicating that is it to be used as a block), Ruby will call to_proc on it in an attempt to make it usable as a block. Symbol#to_proc quite handily returns a Proc that will invoke the method of the corresponding name on whatever is passed to it, thus enabling our little shorthand trick to work.
