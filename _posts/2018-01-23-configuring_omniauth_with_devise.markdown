---
layout: post
title:      "Configuring OmniAuth with Devise"
date:       2018-01-23 18:42:32 +0000
permalink:  configuring_omniauth_with_devise
---


**OmniWhat??**

OmniAuth. It’s a gem for Rails. And it’s dope, for you and your users! You can learn more about it [here](http://github.com/omniauth/omniauth), but basically it allows your users to sign up/log in to your app using a third-party provider (e.g. Facebook, Google, Github, etc.) Now your lazy users don’t have to type as much or remember multiple passwords and you get to leave your users’ sensitive information up to the advanced technology of these trusted powerhouses to protect from hackers.

**And What’s Devise again?**

[Another gem](http://github.com/plataformatec/devise) for Rails. It sprinkles fairy dust all over your User model and makes your life 10x easier if you have lots of authentication needs. Otherwise, it's unnecessary and can do more harm than good.

**Got it. So how can I use both of these at the same time?? **

You’ve created a rails application and now you’re ready to configure OmniAuth with Devise. 

**Step 1.** Add the appropriate gems to your Gemfile and then run bundle install.


![Imgur](https://i.imgur.com/pVOZ7vr.png)


In this example I’d like my users to have the option of logging in with Facebook. You can have a different provider or have multiple different ones, all of which will need to be installed by a separate gem modeling this format.

**Step 2.** Set Up Devise. Type the following commands in your terminal:

	$ rails generate devise:install
	$ rails generate devise User
	$ rake db:migrate

Great! Now you have a User class and all of the associated sign in/sign up forms.

**Step 3.** If you want to require your users to have an account and be logged in before accessing the views in your app, add the following code to you Application Controller:


![Imgur](https://i.imgur.com/5HMzL66.png)


**Step 4.** Add columns to your User table in order to support OmniAuth. Run the following commands in your terminal:

	$ rails g migration AddColumnsToUsers provider uid
	$ rake db:migrate

**Step 5.**  Register your app at your provider’s website. This process might be different depending on your provider, but Google will have all your answers. Put this when prompted to enter a callback URL: http://localhost:3000/users/auth/[provider_name]/callback

**Step 6.** Identify the Client ID and Client Secret from the provider and add them to /config/initializers/devise.rb:


![Imgur](https://i.imgur.com/vnZlVsV.png)


**Step 7**.  Update your User model so that it looks like so:


![Imgur](https://i.imgur.com/HyuC9XD.png)


#from_omniauth makes the user information from the provider account accessible throughout the rest of your app.

**Step 8.**  Create a new controller to pass along the Omniauth callbacks. Create a new file called callbacks_controller.rb: 


![Imgur](https://i.imgur.com/7jpaoZs.png)


**Step 9.** Specify the name of this new controller in your routes:


![Imgur](https://i.imgur.com/vWQ39kg.png)


Now fire up your server and bask in the glory!

