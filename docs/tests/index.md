---
layout: home
title: Tests
---

# Tests

## Unit Tests

Unit tests are used to test individual units of code, such as individual methods or functions. 

They are designed to test the code in isolation, without any dependencies on external systems or services.

- RSpec
- JUnit
- NUnit

```ruby
# Example Unit Test in Ruby using RSpec

describe Calculator do
  describe "#add" do
    it "returns the sum of two numbers" do
      calculator = Calculator.new
      result = calculator.add(2, 3)
      expect(result).to eq(5)
    end
  end
end
```

## Functional Tests

Functional tests are designed to test the functionality of individual features or components of an application. 

These tests are typically written from the perspective of a user or client, and focus on the external behavior of the system. 

They verify that the system behaves as expected when given certain inputs, and that it produces the expected outputs. 

Functional tests are often used to test the behavior of individual methods or functions within the code.

- RSpec 
- Minitest

```ruby
# Example Functional Test in Ruby on Rails

require 'test_helper'

class UsersControllerTest < ActionDispatch::IntegrationTest
  test "should get new" do
    get new_user_url
    assert_response :success
  end

  test "should create user" do
    assert_difference('User.count') do
      post users_url, params: { user: { name: "John", email: "john@example.com", password: "password" } }
    end

    assert_redirected_to user_url(User.last)
  end
end
```

## Integration Tests

Integration tests are used to test the interactions between different components or subsystems of an application. 

They are designed to test how the system works as a whole, and may involve testing the interactions between the front-end and back-end of an application, or the interactions between multiple modules, databases, or external services. 

- Selenium
- Capybara

```ruby
# Example Integration Test in Ruby on Rails using Capybara

require "rails_helper"

RSpec.feature "User Registration", type: :feature do
  scenario "User can register for an account" do
    visit "/users/new"
    fill_in "Email", with: "user@example.com"
    fill_in "Password", with: "password"
    click_button "Create Account"
    expect(page).to have_content("Welcome to our site!")
  end
end
```

## Acceptance Tests

Acceptance tests are used to test the overall behavior of an application from the perspective of a user or client. 

They are designed to test the system as a whole, and may involve testing multiple features or components of the system. They may involve defining scenarios or user stories in natural language

- Cucumber 
- Behave

```ruby
# Example Acceptance Test in Ruby using Cucumber

Feature: User Registration
  Scenario: User can register for an account
    Given I am on the registration page
    When I enter my email and password
    And I click the create account button
    Then I should see a welcome message

    Examples:
      | email            | password |
      | user@example.com | password |
```

## Performance Tests

Performance tests are used to test the performance and scalability of an application. 

They are designed to simulate high loads and stress on the system, and may involve testing the system under heavy traffic or load. 

- JMeter
- Gatling

```ruby
require 'ruby-jmeter'

test do
  threads count: 10, rampup: 5, duration: 60 do
    visit name: 'Home Page', url: 'https://www.example.com/'
  end
end.run(
  path: '/path/to/jmeter/bin',
  gui: false,
  file: 'load_test.jmx',
  log: 'load_test.log'
)
```
