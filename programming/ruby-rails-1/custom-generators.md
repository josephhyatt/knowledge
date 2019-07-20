# Custom Generators

```ruby
# Inside config/application.rb you want to delete the code inside 
# Class Application and add replase with customer generator options
# when using scaffolding

require_relative 'boot'

require "rails"
# Pick the frameworks you want:
require "active_model/railtie"
require "active_job/railtie"
require "active_record/railtie"
require "active_storage/engine"
require "action_controller/railtie"
require "action_mailer/railtie"
require "action_view/railtie"
require "action_cable/engine"
# require "sprockets/railtie"
require "rails/test_unit/railtie"

# Require the gems listed in Gemfile, including any gems
# you've limited to :test, :development, or :production.
Bundler.require(*Rails.groups)

module Flashcards
  class Application < Rails::Application
    config.generators do |g|
      g.orm               :active_record # Uses standard rails default connection to database
      g.template_engine   :erb # Sets templates to erb
      g.test_framework    :test_unit, fixture: false # Defines which gramework we want to use
      g.stylesheets       false # Not requiring stylesheet
      g.javascripts       false # Not requiring javascript
  end
end
```

