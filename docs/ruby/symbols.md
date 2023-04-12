---
layout: home
parent: Ruby
title: Symbols
---

# Symbols

In Ruby, a symbol is an object that represents a name or identifier.

A symbol is denoted by a leading colon (:) followed by a name or identifier, such as :name, :id, or :created_at.

## Symbols vs Strings

Symbols are similar to strings in that they represent text values, but there are some important differences between the two:

1. **Symbols are immutable**, meaning they cannot be changed once they are created. This makes them more efficient than strings for certain use cases.

2. **Symbols are generally used for representing names, identifiers, or keys in a Ruby program**. They are often used as keys in hashes or as method names in method calls.

3. **Symbols are usually compared by identity rather than by value**. This means that two symbols with the same name are considered equal, even if they are different objects.

## When to use?

It is important to note that while symbols can be useful for improving performance and memory efficiency in certain situations, excessive use of symbols can also lead to memory bloat if they are not properly garbage collected, and can make debugging more difficult since they do not contain as much information as strings. 

Therefore, it is generally recommended to use symbols for things that are not likely to change, such as method names and keys in hashes, and to use strings for user input and other mutable data.
