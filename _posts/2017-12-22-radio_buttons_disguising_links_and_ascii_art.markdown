---
layout: post
title:      "Radio Buttons, Disguising Links, & ASCII Art!"
date:       2017-12-22 17:13:11 +0000
permalink:  radio_buttons_disguising_links_and_ascii_art
---


I’ve completed my Sinatra project and if I wasn’t feeling it before, I definitely feel it now: this learning thing works. Up until the Fwitter lab, I was having to regularly consult my notes and the learn readme’s in order to review many of the MVC concepts I was working with. By the time I was ready to build my own app, I felt I finally had the concepts down. I entered a flow state and time flew. It was probably one of the most enjoyable coding experiences I’ve had to date—to feel like I actually knew what I was doing, to be creating something usable with a practical function,  and to gather momentum during the process. There were a few road bumps (duh) trying to find out how to do stuff that hasn’t been covered in our lessons. This post is about sharing the new tricks I learned with you!

**Radio Buttons**

If you’ve reached the ActiveRecord in Sinatra lessons, you know all about forms, post requests, and checkboxes. But with checkboxes, your user can select as many as she wants. What if you want your user to only be able to select one (e.g. yes/no)? Enter radio buttons! In you input tag, set type=”radio”, assign all radio buttons the same name, and assign them to their corresponding value. Here’s a basic example:

![Imgur](https://i.imgur.com/cWLX5hA.png)

If you wanted to manipulate your data based on this user input, you would use the following code (assuming your User class has a legal_status attribute in this example): @user.legal_status = params[:legal_status]


**Disguise Those Ugly Links As Pretty Buttons**

I didn’t like how the basic link in my views looked in the browser. I wanted something a little more sleek and official looking.  Instead of adding a bunch of styling, I simply created yet another form. If your form only includes a “submit” input, then you’re left with a button. The value can be set to whatever you want the text on the button to say.

![Imgur](https://i.imgur.com/3IsWy4Q.png)

Don’t forget to create your post action in your controller! Your post action simply needs to render the page you would like to link to.

**ASCII Fun**

This isn’t really a trick. Just a dope [website](http://picascii.com/).  You can upload any .jpg image and it will convert it into html code in under 10 seconds. Really curious as to how they programmed it. A future research project… That’s all! 



