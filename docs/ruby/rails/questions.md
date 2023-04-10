---
layout: home
parent: Rails
title: Questions
---

# Questions

## N+1 problem

 So if we have N posts, we'll end up making N+1 queries: one to retrieve all the posts, and then one for each post to retrieve its associated user.

This can cause performance issues, especially if we have a large number of posts. To avoid the N+1 problem, we can use eager loading to load the associated users for all posts in a single query. We can do this by modifying our initial query to include the associated users using the includes method like this:

```ruby
<% @posts.each do |post| %>
  <p><strong><%= post.title %></strong></p>
  <p>Written by <%= post.user.name %></p>
<% end %>
```

Problem:

```ruby
@posts = Post.all
```

Solution:

```ruby
@posts = Post.includes(:user).all
```
