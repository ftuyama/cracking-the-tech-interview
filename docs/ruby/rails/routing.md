---
layout: home
parent: Rails
grand_parent: Ruby
title: Routing
---

# Routing

Routing maps URLs to controller actions in Rails. 

It allows you to define the URLs that users can visit in your application, and specify which controller actions should be executed in response to each URL.

## Routes

A route maps a URL to a controller action. 

You can define routes in the config/routes.rb file using methods such as get, post, put, and delete. You can also use placeholders in your routes to capture dynamic segments of the URL.

## Resources 

Resources are a way of defining RESTful routes for a model in your application. 

They provide a standardized way of mapping CRUD (create, read, update, delete) operations to HTTP verbs and URLs. You can define resources using the resources method in your routes file.

## Namespaces 

Namespaces allow you to group related routes under a common prefix. 

This can be useful for organizing your routes and avoiding naming conflicts. You can define namespaces using the namespace method in your routes file.

## Example

```ruby
Rails.application.routes.draw do
  # root route
  root 'home#index'

  # articles routes
  resources :articles do
    resources :comments
  end
  
  # Random routes
  get 'thankyou', to: 'thank_you#index'
  get 'products/:id', to: 'products#show', :as => :products

  # user authentication routes
  devise_for :users, controllers: {
    sessions: 'users/sessions',
    registrations: 'users/registrations',
    passwords: 'users/passwords'
  }

  # API routes
  namespace :api, defaults: { format: :json } do
    namespace :v1 do
      resources :posts, only: [:index, :show]
    end
  end
end
```
