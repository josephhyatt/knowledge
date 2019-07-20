# Starting A Rails Project

```ruby
Rails on Rails Cheat Sheet -- Includes updates from Rails 5.0

1. Open terminal and check versions of Ruby and Rails against 
   production server params or to make sure you are using the 
   most recent stable versions.
  $ ruby -v
  $ rvm list
  $ rvm list known
  $ rvm install ruby 2.3.1
  $ rvm list
  $ ruby -v
  $ gem install rails
  $ rails -v

2. Navigate to where you want to create your app:
  $ cd ~/Sites

3. Rails new Options:
      [--skip-namespace], [--no-skip-namespace]              # Skip namespace (affects only isolated applications)
  -r, [--ruby=PATH]                                          # Path to the Ruby binary of your choice
                                                             # Default: /home/jh/.rbenv/versions/2.5.3/bin/ruby
  -m, [--template=TEMPLATE]                                  # Path to some application template (can be a filesystem path or URL)
  -d, [--database=DATABASE]                                  # Preconfigure for selected database (options: mysql/postgresql/sqlite3/oracle/frontbase/ibm_db/sqlserver/jdbcmysql/jdbcsqlite3/jdbcpostgresql/jdbc)
                                                             # Default: sqlite3
      [--skip-gemfile], [--no-skip-gemfile]                  # Don't create a Gemfile
  -G, [--skip-git], [--no-skip-git]                          # Skip .gitignore file
      [--skip-keeps], [--no-skip-keeps]                      # Skip source control .keep files
  -M, [--skip-action-mailer], [--no-skip-action-mailer]      # Skip Action Mailer files
      [--skip-action-mailbox], [--no-skip-action-mailbox]    # Skip Action Mailbox gem
      [--skip-action-text], [--no-skip-action-text]          # Skip Action Text gem
  -O, [--skip-active-record], [--no-skip-active-record]      # Skip Active Record files
      [--skip-active-storage], [--no-skip-active-storage]    # Skip Active Storage files
  -P, [--skip-puma], [--no-skip-puma]                        # Skip Puma related files
  -C, [--skip-action-cable], [--no-skip-action-cable]        # Skip Action Cable files
  -S, [--skip-sprockets], [--no-skip-sprockets]              # Skip Sprockets files
      [--skip-spring], [--no-skip-spring]                    # Don't install Spring application preloader
      [--skip-listen], [--no-skip-listen]                    # Don't generate configuration that depends on the listen gem
  -J, [--skip-javascript], [--no-skip-javascript]            # Skip JavaScript files
      [--skip-turbolinks], [--no-skip-turbolinks]            # Skip turbolinks gem
  -T, [--skip-test], [--no-skip-test]                        # Skip test files
      [--skip-system-test], [--no-skip-system-test]          # Skip system test files
      [--skip-bootsnap], [--no-skip-bootsnap]                # Skip bootsnap gem
      [--dev], [--no-dev]                                    # Setup the application with Gemfile pointing to your Rails checkout
      [--edge], [--no-edge]                                  # Setup the application with Gemfile pointing to Rails repository
      [--rc=RC]                                              # Path to file containing extra configuration options for rails command
      [--no-rc], [--no-no-rc]                                # Skip loading of extra configuration options from .railsrc file
      [--api], [--no-api]                                    # Preconfigure smaller stack for API only apps
  -B, [--skip-bundle], [--no-skip-bundle]                    # Don't run bundle install
  --webpacker, [--webpack=WEBPACK]                           # Preconfigure Webpack with a particular framework (options: react, vue, angular, elm, stimulus)
      [--skip-webpack-install], [--no-skip-webpack-install]  # Don't run Webpack install

Important options:
  -m, [--template=TEMPLATE] 								 # Path to some application template (can be a filesystem path or URL)
  -T, [--skip-test], [--no-skip-test]                        # Skip test files

3a. Create new repo/app without unit tests 
  $ rails new {name} -T  
  example: $ rails new ruby_thursday -T
  or if needing to a specific version of rails: $ rails _4.1.0_ new ruby_thursday -T

4. Navigate into new app
  $ cd ruby_thursday

5. Set up git
  $ git init

6. Set up Github and make first commit
  copy/paste from Github to create remote repo
  $ git add .
  $ git commit -m "Initial commit"

7. Open app in favorite text editor. 
  $ subl .

8. Set Ruby version in Gemfile
  ruby '2.3.1'

9. Review standard gems change any per preferences
	You need to have Postres installed first -- https://wiki.postgresql.org/wiki/Detailed_installation_guides
  gem 'pg'

10. Set up preferred test and development gems

#Option 1: with 'capybara-webkit'  -- you need to have QT installed first https://github.com/thoughtbot/capybara-webkit/wiki/Installing-Qt-and-compiling-capybara-webkit.

	group :development, :test do
		gem 'pry'
    gem 'pry-nav'
    gem 'pry-rails', '~> 0.3.2'
    gem 'rspec-rails'
 		#other option comes with Rails -- gem 'byebug', platform: :mri
	end	

	group :development do
		gem 'better_errors'
    gem 'binding_of_caller'
		gem 'listen', '~> 3.0.5'
		gem 'letter_opener'
		gem 'spring'
		gem 'spring-watcher-listen', '~> 2.0.0'
	end

  group :test do
   	gem 'capybara-email'
    gem 'capybara-webkit'
		gem 'database_cleaner'
    gem 'factory_girl_rails'
    gem 'faker' #some older RubySnacks reference 'ffaker'
    gem 'simple_bdd'
    gem 'shoulda-matchers'
  end 

#Option 2: with 'selenium-webdriver'
	group :development, :test do
		gem 'pry'
    gem 'pry-nav'
    gem 'pry-rails', '~> 0.3.2'
    gem 'rspec-rails'
 		#other option comes with Rails -- gem 'byebug', platform: :mri
	end	

	group :development do
		gem 'better_errors'
    gem 'binding_of_caller'
		gem 'listen', '~> 3.0.5'
		gem 'letter_opener'
		gem 'spring'
		gem 'spring-watcher-listen', '~> 2.0.0'
	end

  group :test do
    gem 'capybara-email'
    gem 'capybara-webkit'
		gem 'database_cleaner'
    gem 'factory_girl_rails'
    gem 'faker' #some older RubySnacks reference 'ffaker'
    gem 'selenium-webdriver'
    gem 'simple_bdd'
    gem 'shoulda-matchers' 
  end

11. Install the gems
  $ bundle

12. Edit config/database.yml with preferred database and database names
  adapter: postgresql
  
  development:
  <<: *default
  database: db/ruby_thursday_development

  test:
    <<: *default
    database: db/ruby_thursday_test

  production:
    <<: *default
    database: db/ruby_thursday_production


13. Create database
  $ rails db:create  #rake db:create still works too

14. Install rspec
  $ rails generate rspec:install

15. Edit or create rails_helper.rb
  #Replace with below for Option 1: with 'capybara-webkit' 
	ENV['RAILS_ENV'] ||= 'test'
	require File.expand_path('../../config/environment', __FILE__)
	# Prevent database truncation if the environment is production
	abort("The Rails environment is running in production mode!") if Rails.env.production?
  require 'spec_helper'
	require 'rspec/rails'
	require 'capybara/rspec'
	require 'simple_bdd'
	require 'shoulda/matchers'
	Capybara.javascript_driver = :webkit

	ActiveRecord::Migration.maintain_test_schema!

	RSpec.configure do |config|
		config.fixture_path = "#{::Rails.root}/spec/fixtures"

		config.use_transactional_fixtures = false
		
    config.before(:suite) do
		  DatabaseCleaner.strategy = :truncation
		  DatabaseCleaner.clean_with(:truncation)
		end	

		config.before(:each) do
		  DatabaseCleaner.start
		end

		config.after(:each) do
		  DatabaseCleaner.clean
		end

    config.include SimpleBdd, type: :feature
		
		Shoulda::Matchers.configure do |config|
		  config.integrate do |with|
		    with.test_framework :rspec
		    with.library :rails
		  end
		end
		
		config.infer_spec_type_from_file_location!

		config.filter_rails_from_backtrace!		

	end

	#Replace with below for Option 2: with 'selenium-webdriver'
		#Note: if selenium-webdriver gem does not update to newest Firefox version fast enough for you
		#you can download a specific version of Firefox and configure to use that version in tests
		#example: 
			#Capybara.register_driver :selenium do |app|
				#require 'selenium/webdriver'
				#Selenium::WebDriver::Firefox::Binary.path = "/home/user/Sites/firefox46/firefox"
				#Capybara::Selenium::Driver.new(app, :browser => :firefox)
			#end
	ENV['RAILS_ENV'] ||= 'test'
	require File.expand_path('../../config/environment', __FILE__)
	# Prevent database truncation if the environment is production
	abort("The Rails environment is running in production mode!") if Rails.env.production?
	require 'spec_helper'
	require 'rspec/rails'
	require 'capybara/rspec'
	require 'simple_bdd'
	require 'shoulda/matchers'

	ActiveRecord::Migration.maintain_test_schema!

	RSpec.configure do |config|

		config.fixture_path = "#{::Rails.root}/spec/fixtures"

		config.use_transactional_fixtures = false

		config.before(:suite) do
		  DatabaseCleaner.clean_with(:truncation)
		end

		config.before(:each) do
		  DatabaseCleaner.strategy = :transaction
		end

		config.before(:each, :js => true) do
		  DatabaseCleaner.strategy = :truncation
		end

		config.before(:each) do
		  DatabaseCleaner.start
		end

		config.after(:each) do
		  DatabaseCleaner.clean
		end
		
		config.include SimpleBdd, type: :feature
		
		Shoulda::Matchers.configure do |config|
		  config.integrate do |with|
		    with.test_framework :rspec
		    with.library :rails
		  end
		end
		
		config.infer_spec_type_from_file_location!

		config.filter_rails_from_backtrace!	

	end
  

16. Commit set up 
  $ git add .
  $ git commit -m "Set up app with development gems, rspec, and pg"
```

