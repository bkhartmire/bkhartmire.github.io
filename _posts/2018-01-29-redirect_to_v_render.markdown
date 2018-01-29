---
layout: post
title:      "Redirect_to v. Render"
date:       2018-01-29 11:25:55 -0500
permalink:  redirect_to_v_render
---


This one is for my Rails babes. Render and redirect_to are both commonly used in controller actions in order to request a location in your views. 

*Are they interchangeable??* 

**Definitely not, as I just painfully learned!! **

*So then what’s the difference?* 

Let me explain by sharing a mistake I made in my Rails App. 

The app is a platform for reviewing restaurants. Any logged in user may review any restaurant only once. While no user can edit a single restaurant multiple times, users may edit any of their own reviews.  However, reviews have a few validation requirements. So new reviews can only be added if they’re validated, and their updated version must also be valid. 


![Imgur](https://i.imgur.com/THvnZL3.png)


In this controller action, I am checking to see if the input in my edit form is valid. If it is valid, the review is updated, the user is redirected to the restaurant show view, and they receive a notice indicating that the review was successfully edited. If it is not valid, then the user should be redirected to the edit form where a list of all their validation errors should be displayed. Here are my views for reference:


![Imgur](https://i.imgur.com/PBlPnQ0.png)


The form partial:


![Imgur](https://i.imgur.com/KcNU2JJ.png)


So when I try to edit a review, everything runs smoothly if my updated version is valid. If my updated version is invalid however, I get this:


![Imgur](https://i.imgur.com/QwguLN4.png)


Whyyy??! So according to my browser console, @restaurant is nil…That would explain the NoMethodError, but what happened to my variable? Something's fishy…

I'll save you the headache and share the resolution I found 30 minutes later. Everything was fixed when I changed redirect_to on line 38 of my Reviews Controller to render.


![Imgur](https://i.imgur.com/nZFSl4i.png)


By using render instead of redirect_to, my edit view still has access to the variables assigned in my controller action when the new request is sent. Because @review was assigned to the edited_review instance variable I defined in my controller, my edit form now has access to its validation errors and is thus able to correctly display all the error messages. 

 **Redirecting didn’t carry any of that data from my controller to the view page. Redirect_to *re*-requests a new URL. A brand new request was being sent to the edit controller action oblivious to everything my user had already gone through! **

Redirect_to works well on line 34 of my controller action because @review had already been updated. The updated version is saved to my database on line 33, so there’s no need to use render. 

