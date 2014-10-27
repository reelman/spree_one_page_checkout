SpreeOnePageCheckout
====================

Implement one page checkout with Spree. The goal here is to build a solution which is clean and elegant, especially taking into account the ability of the app to be easily updated when new version of Spree comes out.

SpreeOnePageCheckout groups all spree checkout steps in a single view with all the information, each step executes synchronous requests to the server, thus the navigation flow is maintained.


The structure of `Spree` views remains in the same manner, with a pair of execciones:


* To display all the steps in one page, we overload `spree/checkout/edit.html.erb` our application. For these we are basically cycling on each step, the responsible for displaying each views correctly is the parcial `_form_wrapper`.

* We have overwritten the part that contains the login form to add a `hidden` parameters that allow us to discernir if we are in the checkout or not.

* The register view inside the checkout process is modified so that it appears as an extra step in the buying process


Installation
------------

Add spree_one_page_checkout to your Gemfile:

```ruby
gem 'spree_one_page_checkout'
```

Bundle your dependencies and run the installation generator:

```shell
bundle
bundle exec rails g spree_one_page_checkout:install
```

Testing
-------

First bundle your dependencies, then run `rake`. `rake` will default to building the dummy app if it does not exist, then it will run specs. The dummy app can be regenerated by using `rake test_app`.

```shell
bundle
bundle exec rake
```

When testing your applications integration with this extension you may use it's factories.
Simply add this require statement to your spec_helper:

```ruby
require 'spree_one_page_checkout/factories'
```

Copyright (c) 2014 [Acid Labs](http://acid.cl), all rigths reserved.
