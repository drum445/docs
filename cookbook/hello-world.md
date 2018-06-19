# Hello World

{% hint style="warning" %}
First you need an amber project generated with [Amber CLI](../guides/create-new-app.md) or [from scratch](from-scratch.md).
{% endhint %}

This recipe will help you to setup a `Hello World!` response in your `/hello` path.

In your `src/controllers/hello_controller.cr` file use this:

{% code-tabs %}
{% code-tabs-item title="src/controllers/hello\_controller.cr" %}
```ruby
class HelloController < ApplicationController
  def hello
    "Hello Amber!"
  end
end
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Then add a new route in your `config/routes.cr` file:

```ruby
Amber::Server.configure do |app|
  pipeline :web do
    # pipelines...
  end

  routes :web do
    # other routes,,,
    get "/hello", HelloController, :hello
  end
end
```


