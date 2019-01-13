# The Structure of a Rails Application

> **app** - This folder contains your application. Therefore it is the most important folder in Ruby on Rails and it is worth digging into its sub-folders. See the following rows. app/assets Assets basically are your front-end stuff. This folder contains images you use on your website, javascripts for all your fancy front-end interaction and stylesheets for all your CSS making your website absolutely beautiful. app/controllers The controllers sub-directory contains the controllers, which handle the requests from the users. It is often responsible for a single resource type, such as places, users or attendees. Controllers also tie together the models and the views.

> **app/assets** -Assets basically are your front-end stuff. This folder contains images you use on your website, javascripts for all your fancy front-end interaction and stylesheets for all your CSS making your website absolutely beautiful.
>
> **app/controllers** - The controllers subdirectory contains the controllers, which handle the requests from the users. It is often responsible for a single resource type, such as places, users or attendees. Controllers also tie together the models and the views.
>
> **app/helpers** - Helpers are used to take care of logic that is needed in the views in order to keep the views clean of logic and reuse that logic in multiple views. app/mailers Functionality to send emails goes here. app/models The models subdirectory holds the classes that model the business logic of our application. It is concerned with the things our application is about. Often this is data, that is also saved in the database. Examples here are a Person, or a Place class with all their typical behaviour.
>
> **app/mailers** - Functionality to send emails goes here.
>
> **app/models** - The models subdirectory holds the classes that model the business logic of our application. It is concerned with the things our application is about. Often this is data, that is also saved in the database. Examples here are a Person, or a Place class with all their typical behaviour.
>
> **app/views** - The views subdirectory contains the display templates that will be displayed to the user after a successful request. By default they are written in HTML with embedded ruby \(.html.erb\). The embedded ruby is used to insert data from the application. It is then converted to HTML and sent to the browser of the user. It has subdirectories for every resource of our application, e.g. places, persons. These subdirectories contain the associated view files. Files starting with an underscore \(\_\) are called partials. Those are parts of a view which are reused in other views. A common example is \_form.html.erb which contains the basic form for a given resource. It is used in the new and in the edit view since creating something and editing something looks pretty similar.
>
> **config** - This directory contains the configuration files that your application will need, including your database configuration \(in database.yml\) and the particularly important routes.rb which decides how web requests are handled. The routes.rb file matches a given URL with the controller which will handle the request.
>
> **db** - Contains a lot of database related files. Most importantly the migrations subdirectory, containing all your database migration files. Migrations set up your database structure, including the attributes of your models. With migrations you can add new attributes to existing models or create new models. So you could add the favorite\_color attribute to your Person model so everyone can specify their favorite color.
>
> **doc** - Contains the documentation you create for your application. Not too important when starting out.
>
> **lib** - Short for library. Contains code you've developed that is used in your application and may be used elsewhere. For example, this might be code used to get specific information from Facebook.
>
> **log** - See all the funny stuff that is written in the console where you started the Rails server? It is written to your development.log. Logs contain runtime information of your application. If an error happens, it will be recorded here.
>
> **public** - Contains static files that do not contain Ruby code, such as error pages.
>
> **script** - By default contains what is executed when you type in the rails command. Seldom of importance to beginners.
>
> **test** - Contains the tests for your application. With tests you make sure that your application actually does what you think it does. This directory might also be called spec, if you are using the RSpec gem \(an alternative testing framework\).
>
> **vendor** - A folder for software code provided by others \("libraries"\). Most often, libraries are provided as ruby gems and installed using the Gemfile. If code is not available as a ruby gem then you should put it here. This might be the case for jQuery plugins. Probably won't be used that often in the beginning.
>
> **Gemfile** - A file that specifies a list of gems that are required to run your application. Rails itself is a gem you will find listed in the Gemfile. Ruby gems are self-contained packages of code, more generally called libraries, that add functionality or features to your application. If you want to add a new gem to your application, add "gem gem\_name" to your Gemfile, optionally specifying a version number. Save the file and then run bundle install to install the gem.
>
> **Gemfile.lock** - This file specifies the exact versions of all gems you use. Because some gems depend on other gems, Ruby will install all you need automatically. The file also contains specific version numbers. It can be used to make sure that everyone within a team is working with the same versions of gems. The file is auto-generated. Do not edit this file.

