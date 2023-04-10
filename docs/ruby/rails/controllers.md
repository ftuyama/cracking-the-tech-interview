---
layout: home
parent: Rails
title: Controllers
---

# Controllers

Controllers are the glue between the model and the view in Rails. 

They handle user input and manage the flow of data between the model and the view. Some key features of controllers include

## Actions

An action is a method in a controller that handles a user request. 

Actions typically correspond to URLs in your application, and can render views, redirect to other URLs, set flash messages, and more.

## Filters

Filters are a way of specifying code that should be executed before or after a particular action. 

They can be used to authenticate users, set up database connections, and perform other tasks. Filters are defined using methods such as `before_action`, `after_action`, and `around_action`.

## Example

```ruby
class ProductsController < ApplicationController
  def index
    @products = Product.all
  end

  def show
    @product = Product.find(params[:id])
  end

  def new
    @product = Product.new
  end

  def create
    @product = Product.new(product_params)

    if @product.save
      redirect_to @product
    else
      render :new
    end
  end

  def edit
    @product = Product.find(params[:id])
  end

  def update
    @product = Product.find(params[:id])

    if @product.update(product_params)
      redirect_to @product
    else
      render :edit
    end
  end

  def destroy
    @product = Product.find(params[:id])
    @product.destroy

    redirect_to products_path
  end

  private

  def product_params
    params.require(:product).permit(:name, :description, :price)
  end
end
```
