---
layout: home
parent: Rails
grand_parent: Ruby
title: Turbo
---

# Turbo

Rails Turbo is an extension of the Ruby on Rails framework that introduces a set of features for building modern, reactive web applications. 

Turbo is built upon the principles of the Turbolinks library, which provides a seamless, single-page application (SPA)-like experience while preserving the familiar server-rendered nature of Rails. 

It achieves this by using Ajax requests to update only the parts of the page that have changed, rather than reloading the entire page.

## Features

- **Turbo Streams**: Turbo Streams is a mechanism for updating HTML content on the client-side using server-side rendering. It allows you to send small snippets of HTML in response to an action, which are then seamlessly integrated into the existing page on the client-side. This enables real-time updates and a dynamic user experience without the need for building complex JavaScript front-ends.

- **StimulusJS**: Stimulus is a JavaScript framework integrated with Turbo that provides a lightweight way to enhance interactivity in Rails applications. It follows a "just enough JavaScript" approach, allowing you to write small, targeted JavaScript controllers that enhance specific elements or components on the page. Stimulus simplifies the management of JavaScript behavior and facilitates better collaboration between developers working on the back-end and front-end parts of an application.

- **Hotwire**: Hotwire is an umbrella term encompassing Turbo Streams, Stimulus, and other related technologies. It promotes a productive development workflow by combining server-rendered HTML with the benefits of modern JavaScript frameworks. Hotwire allows you to build interactive, reactive interfaces without the need for building and maintaining a separate API or complex JavaScript codebase.

- **Turbo Frames**: Turbo Frames is a Turbo component that allows you to isolate parts of a page and update them independently. It enables you to create reusable components with their own lifecycle, making it easier to manage state and update specific sections of the UI.

- **Turbo Drive**: Turbo Drive is an extension to Turbolinks that enhances the navigation experience in a Turbo-enabled application. It intercepts link clicks and form submissions, allowing for smooth, instant page transitions by loading content via Ajax requests.

## Example

1. We set up the necessary Turbo Streams template in our Rails view. We can define a partial template `_task.html.erb`:

```
<div id="tasks">
  <%= turbo_stream_from @task %>

  <% @tasks.each do |task| %>
    <%= turbo_stream.append "tasks", task %>
  <% end %>
</div>
```

2. In the controller, we handle the task creation and broadcasting of updates using Turbo Streams. Assuming we have a TasksController with a create action:

```
class TasksController < ApplicationController
  def create
    @task = Task.new(task_params)

    if @task.save
      # Broadcast the new task to Turbo Streams
      Turbo::StreamsChannel.broadcast_replace_to(
        @task, 
        target: "tasks"
      )
      # ...
    else
      # ...
    end
  end

  # ...
end
```

3. In the JavaScript part of our Rails application, we can use StimulusJS to handle user interactions and trigger Turbo Streams updates. Assuming we have a tasks_controller.js Stimulus controller:

```
import { Controller } from "stimulus"

export default class extends Controller {
  createTask(event) {
    event.preventDefault();
    const form = event.target;

    Rails.ajax({
      type: form.method,
      url: form.action,
      data: new FormData(form),
      success: () => {
        form.reset();
      }
    });
  }
}
```

4. In our Rails view, we attach the Stimulus controller to the task creation form:

```
<form action="/tasks" method="POST" data-controller="tasks">
  <!-- Form inputs -->
  <input type="text" name="task[title]" required>
  <input type="submit" value="Create Task">
</form>
```
