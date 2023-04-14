---
layout: home
parent: Ruby
title: Polymorphism
---

# Polymorphism

Polymorphism is a concept in object-oriented programming that allows objects of different classes to be treated as if they are objects of the same class. 

This means that objects can be used interchangeably, regardless of their specific class or implementation.

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

## Types

There are two main types of polymorphism:

- **Ad-hoc Polymorphism**: It allows functions with the same name to behave in different ways depending on the type of arguments passed to them. This type of polymorphism is also known as method overloading or operator overloading.

- **Parametric Polymorphism**: It allows functions or data types to be written generically, so that they can handle values of different types or classes without requiring specific implementations for each type. This type of polymorphism is also known as generics or template programming.


## Polymorphism in RoR

In RoR, polymorphic associations allow a model to belong to more than one other model, on a single association. 

### Example

You can use Polymorphic associations to allow comments to belong to either an article or a photo.

```bash
rails generate model Comment content:text commentable:references{polymorphic}
```

The commentable attribute is a Polymorphic association that allows a comment to belong to either an article or a photo.

```ruby
class Comment < ApplicationRecord
  belongs_to :commentable, polymorphic: true
end

class Post < ApplicationRecord
  has_many :comments, as: :commentable
end

class Photo < ApplicationRecord
  has_many :comments, as: :commentable
end
```

These associations allow you to retrieve all comments associated with an article or a photo, using the comments method.

To create a new comment, you would do something like:

```ruby
article = Article.first
comment = article.comments.create(content: "Great article!")

photo = Photo.first
comment = photo.comments.create(content: "Beautiful photo!")
```

This would create a new comment associated with either an article or a photo, depending on which model you call the comments method on.

