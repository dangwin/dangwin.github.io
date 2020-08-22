---
layout: post
title:      "Booleans, and their importance"
date:       2020-08-22 01:27:26 +0000
permalink:  booleans_and_their_importance
---


//Blog 3 // What is something subtle but important about Booleans?

 

To understand why a Boolean is important, we must understand first what a Boolean is. A Boolean is a “binary variable, having two possible values called “true” or “false” When I am reminded of what a Boolean is, I reflect back on all the labs and two projects that I have worked on so far. How many times did I use a Boolean subtly? When did I use Booleans to help de-bug? Why are Booleans used in the first place? These are some questions I would like to get answered.

When using Boolean logic one frequently uses Boolean logic. These operators consists of AND (&&) OR (||) and NOT (!). These operators allow the developer to put in contingencies. If “A” is true then go this route. If “A” is false then go another route. In cases like this and most other cases, a Boolean is so simple, but yet tremendously useful. In Ruby, only nil is false, and everything else is considered true. This includes the integer 0 and an empty array. I came across these so many times while running binding.pry on my code.

De-bugging is a big part of any developer’s workflow and Booleans also play a huge role in it. I remember an instance I had yesterday while working on my Sinatra project. My project kept crashing after submitting an edit to a review and I was unsure why. I ran a binding.pry after my @user = current_user to see what my @user is. It returned nil in the terminal and I thought that was strange. Even though I am logged in as a user right now, my app does not see my user and there must be a disconnect somewhere. I thought to myself why @user is currently false. I quickly back tracked to where I defined my current_user method to see what could’ve gone wrong there. My code for my current_user method was @current_user ||= User.find_by_id(session[:user_id] if session[:user_id]. Going through my debugging process, if I type User.all, I’m able to find all of my Users and therefore it is true or it exists. I know that wasn’t the issue. So I knew it had something to do with my session[:user_id]. I quickly looked in my application controller to see if I had actually even enabled sessions. Lo and behold, I did not. Therefore every time that I would call on current_user, it could never initiate the session because it was never enabled in the first place.

This is one of the many instances that I had to use Booleans to fix my code. Because Booleans are everywhere in our code from the development phase to the debugging phase, we sometimes forget that we’re even using it. Actually, I even forget that I use TRUE/FALSE statements when I use IF/ELSE in my code! How crazy is that?

Back to the blog question, “what is something subtle but important about Booleans?” In my opinion, because we use Booleans so much without even realizing it, it becomes second nature to us and that is why it is so important. Booleans are everywhere in our code. Whether it may be something like does string a == string b or an IF/ELSE statement, Booleans allow the developer to have control over their work flow. It lends a hand in solving issues we may have in our code. Booleans are not just important, they are essential.
