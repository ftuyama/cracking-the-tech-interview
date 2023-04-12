---
layout: home
parent: Rails
grand_parent: Ruby
title: Rspec
---

# Rspec

RSpec is a popular testing framework for Ruby, and is widely used in Rails applications to write tests for models, controllers, and other components of the application. 

RSpec provides a domain-specific language (DSL) for writing tests, which makes it easy to express expectations about the behavior of the application in a clear and concise way.

## Features

One of the key features of RSpec is its use of descriptive language to create "specs" that define the desired behavior of the code being tested. 

Specs are written in a block format, with a "describe" block defining a group of related tests, and an "it" block defining a specific test case. 

RSpec also provides a number of "matchers" that allow you to make assertions about the behavior of the code being tested.

## Example 1

```ruby
RSpec.describe UsersController, type: :controller do
  describe "GET index" do
    it "assigns @users" do
      user = User.create(name: "Test User")
      get :index
      expect(assigns(:users)).to eq([user])
    end

    it "renders the index template" do
      get :index
      expect(response).to render_template("index")
    end
  end
end
```

## Example 2

```ruby
class Order < ApplicationRecord
  has_many :line_items

  def total_price
    line_items.sum(&:price)
  end
end
```

```ruby
RSpec.describe Order, type: :model do
  describe "#total_price" do
    it "calculates the correct total price" do
      order = Order.new
      line_items = [double(price: 10), double(price: 20)]
      allow(order).to receive(:line_items).and_return(line_items)

      expect(order.total_price).to eq(30)
    end
  end
end
```

## Example 3

```ruby
RSpec.describe YourController, type: :controller do
  describe "POST create" do
    context "with invalid parameters" do
      it "returns HTTP 400" do
        post :create, params: { invalid_param: "value" }
        expect(response).to have_http_status(400)
      end
    end
  end
end
```
