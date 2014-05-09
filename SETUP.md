# 3 Steps to deploying a WebApp:
    1 update your app
    2 commit your changes to Git
    3 deploy your app to Heroku
    ! Get in the zone and repeat!

# The Setup:

## Create a Directory For Your Code
	mkdir code
	cd code

## Create a New Rails App
    rails new my_card -O -T --skip-keeps
For this app we won't use a database and we won't be writing tests.

-O flag will skip the default database access framework (ActiveRecord)

-T flag will skip the default testing framework (TestUnit)

## Start the Rails Server
    cd my_card
    rails server
The server will run on port 3000 by default

visit [http://0.0.0.0:3000](http://0.0.0.0:3000) to view the default homepage that gets automatically generated

If you see an error when running the server,
make sure that you didn't already started it in another terminal!

## Stop the rails server
    ^c
visit [http://0.0.0.0:3000](http://localhost:3000) to see that the default homepage is no longer available

## Create a Repo
    git status
    git init
    git status
    git add .
    git status
    git commit -m"initial app"
    git status    
    git log

## Lets Edit The Homepage
    subl .
Go ahead and start the server back up too.

## Add a New Route:
    root 'home#index'
	! refresh the hompage, and notice the error message

## Add home_controller.rb:
	class HomeController < ApplicationController
    end
	! refresh the homepage and notice the error message
	
## Add the index action:
    class HomeController < ApplicationController
      def index
      end
    end
	! refresh the homepage and notice the error message

## Add index.html
    <h1>Hello Earth!</h1>
	! refresh the homepage

## Update Gemfile for deployment to Heroku
    gem 'rails_12factor', group: :production

# Commit Changes to Your Local Repo
    git add config/routes.rb
    git add app/controllers/home_controller.rb
    git add app/views/home/
    git status
    git commit -m"homepage"
    git log

# Deploy your app

## Hosting Concepts
    http://google.com is hosted by google
    http://localhost is a hosted on your local computer, only you can see it
    You can deploy your app to a hosting service so people can see it on the internet

## Create a Heroku Account

## Create an App on Heroku
    visit *http://my-card.herokuapp.com*
(replace my-card with the name of your own app)

## Add Heroku As a Remote Repo
    git remote
    git remote add heroku [git@heroku.com:my-card.git]
    git remote
(replace my-card with the name of your own app)
    
## Push Your Local Repo to Heroku
    git push heroku master
	! refresh the browser page to see your app live on the internet!

## Lets Design your Business Card!
    mkdir app/assets/images
    save your profile pic to app/assets/images/me.png
    design the layout for your card
    Update the HTML for your layout
    Write the css to Style your layout
    Update the HTML to include the content for your card
    Updtae the CSS to style the look and feel for your card
    ! refresh the browser (localhost)!
    
# Commit Changes to Your Local Repo
	git add .
	git commit -m"Design my card"
	
# Deploy your app
    git push heroku master
    ! refresh the browser (heroku app)!
